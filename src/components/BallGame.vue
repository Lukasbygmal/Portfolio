<template>
    <div>
        <canvas ref="canvas" style="width: 100%;" width="400" height="120"></canvas>
    </div>
  </template>

<script>
export default {
  mounted() {
    this.initGame();
  },
  methods: {
    initGame() {
      const canvas = this.$refs.canvas;
      const ctx = canvas.getContext('2d');
      
      // Initial ball position
      let x = canvas.width / 2;
      let y = canvas.height - 30;
      let dx = 2;
      let dy = -2;
      const ballRadius = 10;

      // Draw the ball
      function drawBall() {
        ctx.beginPath();
        ctx.arc(x, y, ballRadius, 0, Math.PI * 2);
        ctx.fillStyle = "#0095DD";
        ctx.fill();
        ctx.closePath();
      }

      // Update the ball position
      function updateBallPosition() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        drawBall();
        x += dx;
        y += dy;
        if (x + dx > canvas.width - ballRadius || x + dx < ballRadius) {
          dx = -dx;
        }
        if (y + dy > canvas.height - ballRadius || y + dy < ballRadius) {
          dy = -dy;
        }
      }

      // Main game loop
      function gameLoop() {
        requestAnimationFrame(gameLoop);
        updateBallPosition();
      }

      gameLoop();
    }
  }
};
</script>
