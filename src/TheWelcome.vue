<script>
import WelcomeItem from './WelcomeItem.vue'
import IconOpenX from './icons/IconOpenX.vue'
import IconCloseX from './icons/IconCloseX.vue'

export default {
  components: {
    WelcomeItem,
    IconOpenX,
    IconCloseX
  },
  methods: {
    toggleVisibility(classTarget) {
      this.hideElement(`${classTarget}`)
      this.showElement(`${classTarget}-open-x`)
      this.hideElement(`${classTarget}-close-x`)
      this.showElement(`${classTarget}-placeholder`)
    },
    hideElement(classTarget) {
      const div = document.querySelector(`.${classTarget}`)
      div.style.display = div.style.display === 'block' ? 'none' : 'block'
    },
    showElement(classTarget) {
      const div = document.querySelector(`.${classTarget}`)
      div.style.display = div.style.display === 'none' ? 'block' : 'none'
    }
  }
}
</script>

<template>
  <img src="@/assets/team.png" alt="Team" />
  <WelcomeItem>
    <template #heading>
      Once upon a time, there was a team that wanted to change the world…
    </template>

    <p>
      In a world teetering on the brink of chaos, where ancient forces and modern technology
      collide, a new era of heroes emerges, destined to shape the fate of humanity. Brought together
      by fate and forged in the fires of battle, they are a diverse assembly of extraordinary
      individuals, each carrying the weight of their own past and the burden of unimaginable power.
      As dark forces rise from the shadows, these unlikely allies must unite, for only together can
      they stand against the impending storm and protect the world from annihilation.
    </p>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <IconOpenX
        class="journey-starts-open-x"
        @click.prevent="toggleVisibility('journey-starts')"
      />
      <IconCloseX
        class="journey-starts-close-x"
        @click.prevent="toggleVisibility('journey-starts')"
      />
    </template>
    <img src="@/assets/journey-start.png" alt="Journey starts" />
    <template #heading>Where it all began…</template>
    <p>
      Alright, gather 'round, folks, and let me spin you a yarn about a little movie called The
      Avengers. Now, imagine you've got a bunch of talented athletes—each one a star in their own
      right—but they’re all playing different sports. You got your Iron Man over here, who’s the
      flashy quarterback, Captain America, the solid, all-American linebacker, and don’t even get me
      started on Thor, who’s like a big ol’ Nordic rugby player with a hammer for a ball. Then
      there’s the Hulk, who’s basically a one-man wrecking crew, Black Widow, the slick striker who
      can take out an entire defense with a single move, and Hawkeye, the archer who’s basically a
      sharpshooter in cleats. But here’s the kicker—these folks have never played together before!
    </p>
    <p class="journey-starts-placeholder">.........</p>
    <div class="journey-starts">
      <p>
        The story kicks off when Loki, who’s Thor’s adopted brother and a bit of a trickster—imagine
        the guy who always pulls pranks in the locker room but with way more malice—decides he’s
        gonna cause some major trouble. Loki gets his hands on this shiny blue cube called the
        Tesseract, which is basically the cosmic equivalent of the ball in Quidditch, except it can
        open portals to other worlds and cause all sorts of mayhem. So, Loki’s plan? Open a portal,
        let a whole army of aliens called the Chitauri come through, and take over Earth. Not
        exactly what you’d call good sportsmanship, right?
      </p>
      <p>
        Now, Nick Fury, who’s the head coach of S.H.I.E.L.D.—think of him as the Bill Belichick of
        superhero wrangling—realizes that this isn’t a problem you can solve with a stern talking-to
        or a timeout. Nope, this calls for some teamwork, and not just any team, but the best of the
        best. So, Fury starts recruiting: first up is Tony Stark, a.k.a. Iron Man, who’s brilliant,
        a bit cocky, and loves the limelight, but also has the heart of a champion. Then there’s
        Captain America, who’s got that old-school charm and a sense of duty that’s as solid as his
        shield. Thor drops in from Asgard—literally—and he’s got some family issues to work out, but
        his loyalty is as strong as his hammer. Banner, who turns into the Hulk when he’s angry (or,
        you know, whenever there’s a need for some heavy lifting), is a bit of a wildcard, but boy
        does he pack a punch. Rounding out the team, you’ve got Black Widow and Hawkeye, who might
        not have superpowers, but they’ve got skills and heart to spare.
      </p>
      <p>
        So, Coach Fury brings them all together, but as you might imagine, it’s not smooth sailing
        from the get-go. These folks are used to playing solo, and teamwork? Well, that’s a whole
        new ball game. They bicker, they clash—heck, at one point, Iron Man and Thor even duke it
        out in a forest, like a couple of linebackers who can’t decide who gets the last slice of
        pizza at a team dinner. But then, just when it looks like this team’s never gonna gel,
        something incredible happens—Agent Coulson, who’s basically the team’s biggest fan, gets
        hurt by Loki. And that, my friends, is the turning point. The Avengers realize they’re not
        just playing for themselves anymore; they’re fighting for something bigger.
      </p>
      <p>
        Now, fast forward to the big showdown in New York City—Loki’s opened the portal, and the
        Chitauri are flooding in like fans at a free concert. It’s chaos! But here’s where the magic
        of teamwork comes in. Iron Man takes to the skies, Captain America coordinates on the
        ground, Thor brings the thunder, Black Widow and Hawkeye are precision personified, and the
        Hulk? Well, let’s just say he smashes like a man possessed. It’s like watching a beautifully
        orchestrated play in the final seconds of a tied game—the kind that makes you leap out of
        your seat and shout, “Now that’s how you play as a team!”
      </p>
      <p>
        In the end, they close the portal, save the day, and take Loki into custody. But the real
        victory? It’s not just about stopping the bad guys. It’s about six extraordinary individuals
        learning to trust each other, to fight as one, and to become something greater than the sum
        of their parts. They go their separate ways at the end, sure, but you just know that when
        the world needs them again, they’ll be there—like a team that knows how to win, even when
        the odds are stacked against them.
      </p>
      <p>
        And that, my friends, is what makes The Avengers such a special flick. It’s not just about
        the action, the quips, or the jaw-dropping special effects. It’s about heart, teamwork, and
        believing that when we come together, there’s no challenge too big, no villain too tough,
        and no city too far gone to save.
      </p>
    </div>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <IconOpenX class="your-own-pack-open-x" @click.prevent="toggleVisibility('your-own-pack')" />
      <IconCloseX
        class="your-own-pack-close-x"
        @click.prevent="toggleVisibility('your-own-pack')"
      />
    </template>
    <img src="@/assets/your-own-pack.png" alt="Your own pack" />
    <template #heading>Finding our pack—or building one</template>
    <p>
      Alrighty, folks, gather 'round, 'cause I'm about to tell ya a tale of teamwork, heart, and a
      little bit of metal mayhem. So, here we are in the second go-round with our favorite group of
      super pals in Avengers: Age of Ultron. Now, imagine you’ve got this team—full of big
      personalities and even bigger hearts—trying to make the world a better place, one punch, kick,
      and clever quip at a time.
    </p>
    <p class="your-own-pack-placeholder">.........</p>
    <div class="your-own-pack">
      <p>
        But then, uh-oh, Tony Stark, that lovable rascal with a heart of gold and a brain that’s
        always working overtime, accidentally cooks up a new problem while trying to solve an old
        one. He builds Ultron, an artificial intelligence that's supposed to be a sort of high-tech
        security blanket for the world. But, as we all know, sometimes blankets come with a few too
        many threads, and this one unravels into a doozy. Ultron decides the best way to protect
        humanity is, well, to wipe out humanity. Yikes!
      </p>
      <p>
        So, what do our heroes do? They do what they do best—they come together, stronger than ever,
        even when things get tough. We got Cap, always the leader with a moral compass that points
        true north; Thor, who’s still as mighty as a thunderstorm on a summer night; Natasha, sharp
        as a tack and quick as a whip; and Hulk, who's, well, still smashing, but with a little more
        heart this time around. And don't forget Hawkeye, the guy with no superpowers but a whole
        lotta spirit, reminding us that even the smallest arrow can make a big difference.
      </p>
      <p>
        Along the way, they pick up a couple of new friends—Pietro and Wanda Maximoff, twins with
        powers that are just as complicated as their past. They're a bit prickly at first, but, as
        we know, everyone’s got a story, and it’s a real treat to see them grow into heroes
        themselves.
      </p>
      <p>
        Now, it’s not all smooth sailing—there are bumps, bruises, and a whole lot of things gettin’
        blown up. But, through it all, the Avengers show us that when you’ve got trust, a good
        heart, and a team that’s more like a family, there’s nothing you can’t overcome—even if what
        you’re overcoming is a sassy robot with a world domination complex.
      </p>
      <p>
        And by the end, the world’s a bit safer, the team’s a bit stronger, and we’re all reminded
        that even the most powerful among us need each other to make it through. So, hats off to the
        Avengers for showing us that with a little grit, determination, and a whole lot of love, you
        can face down just about any challenge—no matter how metal and menacing it might be.
      </p>
    </div>
  </WelcomeItem>

  <WelcomeItem>
    <template #icon>
      <IconOpenX
        class="building-a-dream-open-x"
        @click.prevent="toggleVisibility('building-a-dream')"
      />
      <IconCloseX
        class="building-a-dream-close-x"
        @click.prevent="toggleVisibility('building-a-dream')"
      />
    </template>
    <img src="@/assets/building-a-dream.png" alt="Building a dream" />
    <template #heading>Creating the dream team, to build state-of-the-art products</template>
    <p>
      Alright, team, gather 'round because we've got ourselves a humdinger of a story to tell.
      Imagine this: you’ve got your team of superheroes, right? A real band of misfits who’ve saved
      the world a couple of times already. They’re basically the Premier League of butt-kicking.
      Now, just when you think they can’t get any bigger or better, along comes this purple fella
      named Thanos. He’s got a chin that could grate cheese and a mission to collect these shiny
      little knick-knacks called Infinity Stones. And lemme tell ya, these stones? They're more
      powerful than a full cup of Earl Grey on a chilly morning.
    </p>
    <p class="building-a-dream-placeholder">.........</p>
    <div class="building-a-dream">
      <p>
        Now, Thanos, bless his heart, thinks he’s doing the right thing by trying to wipe out half
        the universe. Something about balance, like a teeter-totter, but the stakes are just a tad
        higher. Our Avengers, though, they’re not gonna stand for that. They rally together like
        Richmond on a comeback streak. You’ve got Cap, Iron Man, Thor, and even the new kids like
        Doctor Strange and Spider-Man. They’re all in this together, playing like they’ve got one
        heart beating in a giant superhero chest.
      </p>
      <p>
        But here’s the thing, folks: sometimes even your best just isn’t enough. And Thanos? Well,
        he’s like that one team that just has your number no matter what you do. He snaps his
        fingers (literally) and poof, half of everyone just vanishes. I know, it’s rough. Like
        losing a match in the final seconds after a hard-fought game. But remember, this isn’t the
        end of the story. It’s just halftime, and we all know the best teams come out swinging in
        the second half.
      </p>
      <p>
        So keep your heads up, believe in the power of teamwork, and don’t forget: even when things
        seem bleak, there’s always a comeback waiting around the corner. Now, who’s up for a round
        of biscuits?
      </p>
    </div>
  </WelcomeItem>
</template>

<style scoped>
img {
  padding: 6rem;
  justify-content: center;
}

div {
  display: none;
}

.journey-starts-open-x,
.your-own-pack-open-x,
.building-a-dream-open-x {
  display: block;
}

.journey-starts-close-x,
.your-own-pack-close-x,
.building-a-dream-close-x {
  display: none;
}
</style>
