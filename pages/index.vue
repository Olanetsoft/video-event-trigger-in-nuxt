<template>
  <div class="flex justify-center items-center h-screen space-x-10">
    <div class="rounded overflow-hidden shadow-lg mb-4 content-center">
      <div class="px-6 py-4 pb-2">
        <div class="font-bold text-xl mb-2">Feedback Form Trigger</div>
        <video
          id="video-player"
          controls
          autoplay
          muted
          width="500px"
          class="width-full"
        ></video>
      </div>
    </div>

    <Form v-if="ended"></Form>
  </div>
</template>

<script>
import Form from "../components/Form.vue";
export default {
  data() {
    return {
      cld: null,
      player: null,
      video: "samples/animals/testvid",
      ended: null,
    };
  },

  mounted() {
    this.cld = cloudinary.Cloudinary.new({
      cloud_name: process.env.NUXT_ENV_CLOUDINARY_CLOUD_NAME,
      secure: true,
    });

    this.player = this.cld.videoPlayer("video-player", {
      analytics: {
        events: ["ended"],
      },
    });

    this.player.source(this.video);

    this.player.on("ended", () => {
      this.ended = true;
    });
  },
  components: {
    Form,
  },
  name: "IndexPage",
};
</script>
