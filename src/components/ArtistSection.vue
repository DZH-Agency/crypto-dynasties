<template>
  <div class="artist-wrapper">
    <div class="container">
      <div class="artist">
        <div class="artist-img">
          <img src="@/assets/img/ArtistSection/artistImg.png" alt="artist">
          <a href="https://www.instagram.com/nuxer.eth/" target="_blank">@nuxer.eth</a>
        </div>
        <div class="artist-info">
          <h3 class="artist-info__heading">
            Artist
            <img src="@/assets/img/ArtistSection/star.png" alt="" class="artist-info__star-img">
          </h3>
          <div class="artist-info__description">
            <strong>Nuxer</strong> is a self-taught 3D artist and creative junkie, he has spent the last 7 years of his career exploring and sharpening his craft to push the boundaries of the CGI environment. His art is deeply inspired by futuristic and minimalistic approaches that combine powerful shifts between the absence of color and vibrant hues that create a unique visual impact. He approached every piece with a special attention to detail, so the viewer is allowed to discover the intricate nature of computer-generated imagery.
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ArtistSection"
}
</script>

<style scoped lang="scss">
@import "~@/assets/scss/components/ArtistSection.scss";
</style>