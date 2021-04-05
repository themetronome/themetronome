<script>
  import List from './List.svelte'
  import Certificates from './Certificates.svelte'
  import Projects from './Projects.svelte'
  import Hand from './Hand.svelte'

  const avatar = './static/avatar.jpg'
  const ghCF = './static/GrasshopperCodingFundamentalsCertificate.pdf'
  const ghCF2 = './static/GrasshopperCodingFundamentalsIICertificate.pdf'
  const ghCF4 = './static/GrasshopperIntrotoInterviewingCertificate.pdf'
  const skills = [
    'javascript, typescript',
    'react',
    'node.js',
    'scss, styled-components',
    'webpack, rollup',
    'git',
  ]

  const social = [
    { name: 'github', link: 'https://github.com/themetronome' },
    { name: 'telegram', link: 'https://t.me/themetronome' },
    { name: 'vasyayp@yandex.ru', link: 'mailto:vasyayp@yandex.ru' },
  ]

  const courses = {
    fundamentals: [
      {
        name: 'js coding fundamentals',
        link: ghCF,
        year: '2019',
        company: 'google',
      },
      {
        name: 'js coding fundamentals',
        link: ghCF2,
        year: '2019',
        company: 'google',
      },
    ],
    other: [
      {
        name:
          'intro to interviewing. at the end of this course i solved challenging google interview question.',
        link: ghCF4,
        year: '2019',
        company: 'google',
      },
    ],
  }
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
      <h2 class="position">frontend engineer</h2>
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
    <block>
      <h3 class="title">certificates</h3>
      <Certificates {courses} />
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
