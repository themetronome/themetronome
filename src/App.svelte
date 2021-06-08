<script>
  import List from './List.svelte'
  import Hand from './Hand.svelte'

  const avatar = './static/avatar.jpg'
  const skills = [
    'javascript',
    'typescript'
  ]

  const social = [
    { name: 'github', link: 'https://github.com/themetronome' },
    { name: 'telegram', link: 'https://t.me/themetronome' },
    { name: 'vasyayp@yandex.ru', link: 'mailto:vasyayp@yandex.ru' },
  ]

</script>

<container>
  <div class="main">
    <visually-hidden className="visually-hidden"> Vladislav Bukatov's website </visually-hidden>
    <div class="centered">
      <!-- svelte-ignore a11y-img-redundant-alt -->
      <img class="avatar" src={avatar} width="150" height="150" alt="Vladislav Bukatov's photo" />
      <Hand />
    </div>

    <div class="centered">
      <h1>Vladislav Bukatov</h1>
      <h2 class="position">web engineer</h2>
    </div>
    <block>
      <h3 class="title">links</h3>
      <List elements={social} />
    </block>
    <block>
      <h3 class="title">skills</h3>
      <ul>
        {#each skills as skill}
          <li class="skill-item">{skill}</li>
        {/each}
      </ul>
    </block>
  </div>
</container>

<style>
  :global(html) {
    background-color: rgba(242, 242, 230, 0.1);
    color: #242535;
    font-family: 'Helvetica Neue', sans-serif;
  }
  container {
    max-width: 900px;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    padding: 32px;
    font-family: 'Montserrat', sans-serif;
    font-size: 16px;
    line-height: 24px;
  }
  visually-hidden {
    position: absolute;
    width: 1px;
    height: 1px;
    margin: -1px;
    border: 0px;
    padding: 0px;
    clip: rect(0 0 0 0);
    overflow: hidden;
  }
  block {
    align-items: center;
    flex-direction: column;
  }
  .centered {
    text-align: center;
  }
  .position {
    color: hotpink;
  }
  .title {
    color: hotpink;
  }
  .main {
    width: 400px;
  }
  h1 {
    margin-bottom: 8px;
  }
  h2 {
    margin: 0 0 8px;
  }
  h3 {
    font-size: 22px;
    font-weight: bold;
    margin: 28px 0 14px;
  }
  @media (max-width: 500px) {
    container {
      font-size: 14px;
    }
    .avatar {
      width: 100px;
      height: 100px;
    }
    .main {
      width: 300px;
    }
  }
</style>
