<template>
    <div ref="plane" class="airplane" :style="{
        transform: `translate(${x}px, ${y}px) rotate(${rotation}deg)`,
        left: '-45px',
        top: '-45px'
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
            const lerp = 0.12;

            this.x += (this.targetX - this.x) * lerp;
            this.y += (this.targetY - this.y) * lerp;

            const dx = this.targetX - this.x;
            const dy = this.targetY - this.y;
            const targetRotation = Math.atan2(dy, dx) * (180 / Math.PI) + 90;

            let rotationDiff = targetRotation - this.rotation;
            if (rotationDiff > 180) rotationDiff -= 360;
            if (rotationDiff < -180) rotationDiff += 360;

            this.rotation += rotationDiff * lerp;

            while (this.rotation > 180) this.rotation -= 360;
            while (this.rotation < -180) this.rotation += 360;

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
    transform-origin: center center;
}

.airplane img {
    width: 90px;
    height: auto;
    display: block;
}
</style>