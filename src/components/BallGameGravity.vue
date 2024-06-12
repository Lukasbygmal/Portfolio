<template>
    <div>
    <canvas ref="canvas" width="800" height="400"
            @mouseover="handleMouseOver"
            @mouseleave="handleMouseLeave"></canvas>
  </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        dragging: false,
        dragOffsetX: 0,
        dragOffsetY: 0,
        dragStartX: 0 // New property to store the initial X position when dragging starts
      };
    },
    mounted() {
      this.canvas = this.$refs.canvas;
      this.ctx = this.canvas.getContext('2d');
      
      this.ball = {
        x: 200,
        y: 50,
        radius: 20,
        velocityX: 0, // Horizontal velocity
        velocityY: 0,
        gravity: 0.2, // Decreased gravity
        bounce: -0.7
      };
      
      this.canvas.addEventListener('mousedown', this.pickupBall);
      this.canvas.addEventListener('mouseup', this.dropBall);
      
      this.animationLoop();
    },
    methods: {
        handleMouseOver(event) {
            const rect = this.canvas.getBoundingClientRect();
            const mouseX = event.clientX - rect.left;
            const mouseY = event.clientY - rect.top;
      
            const distance = Math.sqrt((mouseX - this.ball.x) ** 2 + (mouseY - this.ball.y) ** 2);
            if (distance < this.ball.radius) {
                this.canvas.style.cursor = 'pointer'; // Change cursor to pointer when over the ball
            } else {
            this.canvas.style.cursor = 'default'; // Reset cursor to default when not over the ball
            }
        },
        handleMouseLeave() {
            this.canvas.style.cursor = 'default'; // Reset cursor to default when leaving canvas
        },
      animationLoop() {
        this.update();
        this.draw();
        requestAnimationFrame(this.animationLoop);
      },
      update() {
        if (this.dragging) return; // Don't update if dragging
  
        // Check for collision with walls
        if (this.ball.x - this.ball.radius <= 0 || this.ball.x + this.ball.radius >= this.canvas.width) {
            this.ball.velocityX *= this.ball.bounce; // Reverse horizontal velocity
        }
  
        // Check for collision with roof
        if (this.ball.y - this.ball.radius <= 0) {
            this.ball.velocityY *= this.ball.bounce; // Reverse vertical velocity
            this.ball.y = this.ball.radius; // Prevent ball from going above the roof
        }
  
  // Check for collision with floor
  if (this.ball.y + this.ball.radius >= this.canvas.height) {
    this.ball.velocityY *= this.ball.bounce; // Bounce the ball
    this.ball.y = this.canvas.height - this.ball.radius; // Prevent ball from going below the floor
  } else {
    this.ball.velocityY += this.ball.gravity; // Apply gravity
  }
  
  this.ball.x += this.ball.velocityX; // Update horizontal position
  this.ball.y += this.ball.velocityY; // Update vertical position
}
,
      draw() {
        this.ctx.clearRect(0, 0, this.canvas.width, this.canvas.height);
        this.ctx.beginPath();
        this.ctx.arc(this.ball.x, this.ball.y, this.ball.radius, 0, Math.PI * 2);
        this.ctx.fillStyle = 'red';
        this.ctx.fill();
        this.ctx.closePath();
      },
      pickupBall(event) {
        const rect = this.canvas.getBoundingClientRect();
        const mouseX = event.clientX - rect.left;
        const mouseY = event.clientY - rect.top;
        
        const distance = Math.sqrt((mouseX - this.ball.x) ** 2 + (mouseY - this.ball.y) ** 2);
        if (distance < this.ball.radius) {
          this.dragging = true;
          this.dragOffsetX = this.ball.x - mouseX;
          this.dragOffsetY = this.ball.y - mouseY;
          this.dragStartX = this.ball.x; // Store the initial X position when dragging starts
          this.canvas.addEventListener('mousemove', this.moveBall);
        }
      },
      moveBall(event) {
  const rect = this.canvas.getBoundingClientRect();
  const mouseX = event.clientX - rect.left;
  const mouseY = event.clientY - rect.top;
  
  const draggedDistanceX = mouseX - (this.ball.x - this.dragOffsetX);
  const draggedDistanceY = mouseY - (this.ball.y - this.dragOffsetY);
  
  // Scale down the horizontal velocity to a fraction of the dragged distance
  const dragFactor = 0.1; // Adjust this value to control the sensitivity of horizontal dragging
  this.ball.velocityX = draggedDistanceX * dragFactor;
  this.ball.velocityY = draggedDistanceY * dragFactor; // We still need to calculate vertical velocity for gravity
  
  this.ball.x = mouseX + this.dragOffsetX;
  this.ball.y = mouseY + this.dragOffsetY;
}
,
      dropBall() {
        this.dragging = false;
        this.canvas.removeEventListener('mousemove', this.moveBall);
      }
    }
  };
  </script>
  
  <style scoped>
  canvas {
    border: 1px solid black;
  }
  </style>
  