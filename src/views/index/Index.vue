<template>
    <div class="index-container">
        <div class="a">
            aaaa
            <div class="b">bbbb</div>
        </div>
        <a-space wrap>
            <a-button type="primary">Primary Button</a-button>
            <a-button>Default Button</a-button>
            <a-button type="dashed">Dashed Button</a-button>
            <a-button type="text">Text Button</a-button>
            <a-button type="link">Link Button</a-button>
        </a-space>
        <div class="pt-[40px] bg-red-500 dark:bg-gray-800">sdfsdfss</div>
        <div class="w-[100px] h-[100px] rounded-ful"></div>
    </div>
</template>
<script setup lang="ts"></script>
<style lang="scss" scoped>
.a {
    background-color: red;
    .b {
        background-color: blue;
    }
}
</style>
