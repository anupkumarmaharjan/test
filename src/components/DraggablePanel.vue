<template>
    <div class="wrapper" @mouseUp="endDragging()">
        <div class="click-to-zoom">
            <i class="fi flaticon-maximize"></i>
        </div>
        <div class="click-to-close">
            <i class="fi flaticon-cancel"></i>
        </div>
        <div class="div1" :style="{width: `${dividerPosition}%`}">
        </div>
        <div class="divider" :style="{left: `${dividerPosition}%`}" @mouseDown="startDragging()">
        </div>
        <div class="center" :style="{width: `${100 - dividerPosition}%`}">
            <div class="div2"></div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'DraggablePanel',
  props: {
    dividerPosition: Number
  },
  methods: {
        handleDragging(e) {
            const percentage = (e.pageX / window.innerWidth) * 100

            if (percentage >= 10 && percentage <= 90) {
                this.dividerPosition = percentage.toFixed(2)
            }
        },
        startDragging() {
            document.addEventListener('mousemove', this.handleDragging)
        },
        endDragging() {
            document.removeEventListener('mousemove', this.handleDragging)
        },
    }
}
</script>