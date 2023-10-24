<script>
    $: userIn = ''
</script>

<style>
    @font-face {
        font-family:'Noto Sans', sans-serif;
        font-style:normal;
        font-weight: 400;
        src: url("https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@0,200;0,300;0,400;0,700;1,200;1,500&display=swap");
    }
    .app-template {
        width:85vw;
        height: 85vh;
        background: rgb(17, 17, 17);
        border: 1px solid rgba(3, 3, 3, .8);
        border-radius: 5px;
        color: #e7e7e7;
    }
    /* .blinking-cursor {
        color: transparent;
        background-image: green;
        animation: blink 1.5s infinite;
    }

    @keyframes blink {
    0% {
      opacity: 0; 
    }

    100% {
      opacity: 1;
    }
  } */
  .header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  user-select: none;
  padding: .125rem;
  margin: .125rem;
  background: rgb(3, 3, 3);
  border-right: rgb(3,3,3) solid .5rem;
  font-size: .825rem;
}
  span {
    padding: .125rem;
  }
  .title-handle {
    flex-grow: 0;
  }
  spacer {
    flex-grow: 1;
  }
  .content-window {
    padding-bottom:.5rem;
        padding-left: .5rem;
        padding-right:.5rem;
  }
</style>

<section class='app-template'>
    <div class="header">
      <span class='title-icon las la-2x la-terminal'></span>
      <span class="title-handle">customTerminal>(/home/usr/Armadillo_Datalog)</span>
      <spacer />
      <div class="facade-nav-buttons">
        <span class="lar la-2x la-window-minimize"></span>
        <span class="lar la-2x la-window-restore"></span>
        <span class="lar la-2x la-window-close"></span>
      </div>
    </div>
    <div class='content-window'>
      <div class='animation-box'> $</div>
      <div class='interpreter'>
        <input type="text" bind:value={userIn}/><p>{ userIn }</p>
      </div>
    </div>
</section>