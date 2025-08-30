<template>
    <div ref="plane" class="airplane" :style="{
        transform: `translate(${x}px, ${y}px) rotate(${rotation}deg)`,
    }">
        <img src="@/assets/plane.png" alt="airplane" />
    </div>
</template>

<script>
export default {
    name: 'AirplaneHandler',
    data() {
        return {
            x: 0,
            y: 0,
            targetX: 0,
            targetY: 0,
            rotation: 0,
            animationId: null
        }
    },
    mounted() {
        this.initPosition();
        window.addEventListener('mousemove', this.handleMouseMove);
        this.animate();
    },
    beforeUnmount() {
        window.removeEventListener('mousemove', this.handleMouseMove);
        if (this.animationId) {
            cancelAnimationFrame(this.animationId);
        }
    },
    methods: {
        initPosition() {
            this.x = this.targetX = window.innerWidth / 2;
            this.y = this.targetY = window.innerHeight / 2;
        },
        handleMouseMove(e) {
            this.targetX = e.clientX;
            this.targetY = e.clientY;
        },
        animate() {
            const lerp = 0.1;

            
            this.x += (this.targetX - this.x) * lerp;
            this.y += (this.targetY - this.y) * lerp;

            const dx = this.targetX - this.x;
            const dy = this.targetY - this.y;
            const targetRotation = Math.atan2(dy, dx) * (180 / Math.PI);

            let rotationDiff = targetRotation - this.rotation;
            if (rotationDiff > 180) rotationDiff -= 360;
            if (rotationDiff < -180) rotationDiff += 360;

            this.rotation += rotationDiff * lerp;

            this.animationId = requestAnimationFrame(this.animate);
        }
    }
}
</script>

<style scoped>
.airplane {
    position: fixed;
    pointer-events: none;
    z-index: 999;
    transform-origin: center;
}

.airplane img {
    width: 40px;
    height: 40px;
    display: block;
}
</style>