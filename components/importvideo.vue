<template>
  <div>
    <input type="file" @change="handleFileInputChange">
    <video v-if="videoUrl" controls>
      <source :src="videoUrl" type="video/mp4">
      Your browser does not support the video tag.
    </video>
  </div>
</template>

<script>
export default {
  data() {
    return {
      videoUrl: null
    };
  },
  methods: {
    handleFileInputChange(event) {
      const file = event.target.files[0];
      if (file && file.type.includes('video')) {
        this.videoUrl = URL.createObjectURL(file);
      } else {
        this.videoUrl = null;
      }
    }
  }
};
</script>
