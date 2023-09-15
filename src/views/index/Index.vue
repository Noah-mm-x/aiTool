<template>
    <div class="index-container">
        <canvas id="myCanvas" width="800" height="600"></canvas>
    </div>
</template>
<script setup lang="ts">
import { onMounted } from 'vue';
onMounted(async () => {
    const image = new Image();
    image.src = 'https://img0.baidu.com/it/u=1906237490,1944644729&fm=253&fmt=auto&app=138&f=JPEG?w=717&h=500';
    await image.onload;

    const canvas: any = document.querySelector('#myCanvas');
    const context = canvas.getContext('2d');
    context.drawImage(image, 0, 0);
    // 将图片转换为Base64编码

    let isDragging = false;
    let initialMouseX: number, initialMouseY: number;
    let initialImageX: number, initialImageY: number;
    let imageX = 0,
        imageY = 0;

    canvas.addEventListener('mousedown', function (event: MouseEvent) {
        isDragging = true;
        initialMouseX = event.clientX;
        initialMouseY = event.clientY;
        initialImageX = imageX;
        initialImageY = imageY;
    });

    canvas.addEventListener('mousemove', function (event: MouseEvent) {
        if (isDragging) {
            const offsetX = event.clientX - initialMouseX;
            const offsetY = event.clientY - initialMouseY;
            imageX = initialImageX + offsetX;
            imageY = initialImageY + offsetY;
            redrawCanvas();
        }
    });

    canvas.addEventListener('mouseup', function () {
        isDragging = false;
    });
    function redrawCanvas() {
        context.clearRect(0, 0, canvas.width, canvas.height);
        context.drawImage(image, imageX, imageY);
    }
});
</script>
<style lang="scss" scoped></style>
