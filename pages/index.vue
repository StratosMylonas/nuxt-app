<template>
  <div>
    <h3>Δημιουργία ® έργων για</h3>
    <h1>Branding</h1>
    <div>
      <table>
        <tr>
          <td>
            <img src="~/assets/images/image1.png" alt="" />
          </td>
          <td>
            <img src="~/assets/images/image2.png" alt="" />
          </td>
          <td>
            <img src="~/assets/images/image3.png" alt="" />
          </td>
          <td>
            <img src="~/assets/images/image4.png" alt="" />
          </td>
        </tr>

        <tr>
          <td>
            <p>Etolea</p>
          </td>
          <td>
            <p>Omni</p>
          </td>
          <td>
            <p>Commit</p>
          </td>
          <td>
            <p>Fresco</p>
          </td>
        </tr>

        <tr>
          <td>
            <p>Branding/Packaging</p>
          </td>
          <td>
            <p>Branding/Webdesign</p>
          </td>
          <td>
            <p>Branding/Webdesign</p>
          </td>
          <td>
            <p>Branding/Webdesign</p>
          </td>
        </tr>
      </table>
    </div>
    <NuxtLink to="/blog">Blog</NuxtLink>
    <br />
    <NuxtLink to="/websites">Websites</NuxtLink>
    <br />
    <NuxtLink to="/brandings">Brandings</NuxtLink>
    <br />
    <NuxtLink to="/packages">Packages</NuxtLink>
    <br />
    <NuxtLink to="/pixiTest">PixiJS</NuxtLink>

    <br />
    <button class="glow" type="button">Glow</button>
  </div>
</template>

<style>
.glow {
  margin-top: 100px;
  width: 220px;
  height: 50px;
  border: none;
  outline: none;
  color: #fff;
  background: #111;
  cursor: pointer;
  position: relative;
  z-index: 0;
  border-radius: 10px;
}

.glow:before {
  content: "";
  background: linear-gradient(
    45deg,
    #ff0000,
    #ff7300,
    #fffb00,
    #48ff00,
    #00ffd5,
    #002bff,
    #7a00ff,
    #ff00c8,
    #ff0000
  );
  position: absolute;
  top: -2px;
  left: -2px;
  background-size: 400%;
  z-index: -1;
  filter: blur(5px);
  width: calc(100% + 4px);
  height: calc(100% + 4px);
  animation: glowing 20s linear infinite;
  opacity: 0;
  transition: opacity 0.3s ease-in-out;
  border-radius: 10px;
}

.glow:active {
  color: #000;
}

.glow:active:after {
  background: transparent;
}

.glow:hover:before {
  opacity: 1;
}

.glow:after {
  z-index: -1;
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  background: #111;
  left: 0;
  top: 0;
  border-radius: 10px;
}

@keyframes glowing {
  0% {
    background-position: 0 0;
  }
  50% {
    background-position: 400% 0;
  }
  100% {
    background-position: 0 0;
  }
}
</style>
