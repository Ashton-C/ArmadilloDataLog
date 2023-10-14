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
    .content-window {
        width:85vw;
        height: 85vh;
        background: rgba(0, 0, 0, 0.6);
        padding: .75rem;
        border: 1px solid rgba(255, 255, 255, 0.2);
        border-radius: 5px;
        color: #e7e7e7;
    }
    .blinking-cursor {
        color: transparent;
        background-image: linear-gradient(45deg, #fbda61 0%, #ff5acd 100%);
        animation: blink 1.5s infinite;
    }

    @keyframes blink {
    0% {
      opacity: 0; 
    }

    100% {
      opacity: 1;
    }
  }
  .header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 0.5em;
  padding: 0.125em;
  padding-right: 0.25em;
  user-select: none;
  background: rgba(0, 78, 31, 0.5);
}
.icon {
  max-width: 20px;
  min-width: 20px;
  width: 20px;
  margin: 0.25em;
  aspect-ratio: 1/0.85;
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;
}
.header .icon, w-window .header .title,  w-window .header .icons {
  flex: 1;
}
</style>

<section class='content-window'>
    <div class="header" style="opacity: 1;">
        <span class="icon handle" style="background-image: url(&quot;data:image/png;base64,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&quot;); opacity: 1;"></span>
        <span class="title handle" style="opacity: 1;">Command Prompt</span>
        <spacer style="opacity: 1;">
            <div class="icons" style="opacity: 1;">
              <span class="button button-min" data-bs-toggle="tooltip" title="" data-bs-original-title="Minimize" aria-label="Minimize" style="opacity: 1;"><svg class="min-icon" aria-hidden="true" focusable="false" data-prefix="fas" data-icon="minus" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" height="10" style="opacity: 1;"><path fill="currentColor" d="M400 288h-352c-17.69 0-32-14.32-32-32.01s14.31-31.99 32-31.99h352c17.69 0 32 14.3 32 31.99S417.7 288 400 288z" style="opacity: 1;"></path></svg></span>
              <span class="button button-max" data-bs-toggle="tooltip" title="" data-bs-original-title="Maximize" aria-label="Maximize" style="opacity: 1;"><svg class="max-icon" aria-hidden="true" focusable="false" data-prefix="far" data-icon="square" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" height="13" style="opacity: 1;"><path fill="currentColor" d="M384 31.1H64c-35.35 0-64 28.65-64 63.1v320c0 35.35 28.65 64 64 64h320c35.35 0 64-28.65 64-64v-320C448 60.65 419.3 31.1 384 31.1zM400 416c0 8.822-7.178 16-16 16H64c-8.822 0-16-7.178-16-16V96c0-8.822 7.178-16 16-16h320c8.822 0 16 7.178 16 16V416z" style="opacity: 1;"></path></svg></span>
              <span class="button button-close" data-bs-toggle="tooltip" title="" data-bs-original-title="Close" aria-label="Close" style="opacity: 1;"><svg class="close-icon" aria-hidden="true" focusable="false" data-prefix="fas" data-icon="xmark" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512" height="14" style="opacity: 1;"><path fill="currentColor" d="M310.6 361.4c12.5 12.5 12.5 32.75 0 45.25C304.4 412.9 296.2 416 288 416s-16.38-3.125-22.62-9.375L160 301.3L54.63 406.6C48.38 412.9 40.19 416 32 416S15.63 412.9 9.375 406.6c-12.5-12.5-12.5-32.75 0-45.25l105.4-105.4L9.375 150.6c-12.5-12.5-12.5-32.75 0-45.25s32.75-12.5 45.25 0L160 210.8l105.4-105.4c12.5-12.5 32.75-12.5 45.25 0s12.5 32.75 0 45.25l-105.4 105.4L310.6 361.4z" style="opacity: 1;"></path></svg></span>
            </div>
        </spacer>
    </div>
    <div class='animation-box'> $</div>
    <div class='interpreter'>
        <input type="text" bind:value={userIn}/><span class='blinking-cursor'>&#9614;</span><p>{ userIn }</p>
    </div>
</section>