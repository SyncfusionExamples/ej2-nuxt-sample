<template>
  <footer class="Footer">
    <div class="Footer__Author container">
      {{ $store.state.lang.footer.authors }}:
      <a href="https://github.com/Atinux" target="_blank">@Atinux</a>
      &amp;
      <a href="https://github.com/alexchopin" target="_blank">@alexchopin</a>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.Footer
{
  text-align: center;
  background: #f6f6f6;
  padding-top: 50px;
  &__Sponsors {
    max-width: 700px;
    padding-bottom: 10px;
    margin: 0px auto;
    h3 {
      color: #999;
      font-weight: 600;
      margin: 0 0 10px;
    }
    &__Link {
      display: inline-block;
      position: relative;
      margin: 20px 15px 0;
      height: 60px;
      img {
        display: inline-block;
        vertical-align: middle;
        height: 100%;
        transition: all 0.3s ease;
        filter: grayscale(100%);
        opacity: 0.66;
        &:hover {
          filter: none;
          opacity: 1;
        }
      }
    }
    &__Become {
      padding-bottom: 40px;
    }
  }
  &__Links
  {
    text-align: center;
    background-color: #35495E;
    color: #eee;
    padding: 15px;
    letter-spacing: 0.5px;
  }
  &__Author
  {
    width: 100%;
    background-color: darken(#35495E, 10%);
    margin: 0;
    font-size: 14px;
    text-align: center;
    padding: 15px;
    color: #9aabb1;
    letter-spacing: 0.5px;
    font-weight: 400;
    a
    {
      color: #9aabb1;
      &:hover
      {
        color: #41b883;
      }
    }
  }
}
</style>
