<script>
import Cite from "$lib/components/Cite.svelte";
</script>

<main>
    <div class="container h-full mx-auto flex justify-center items-center md:w-1/2">
        <div class="space-y-5 mt-5">
            <h1>Data Art</h1>
            <p>
            Data art is an emerging field that takes raw data from computer science and transforms it into visually
            compelling narratives using art. These pieces not only captivate audiences but enhance the understanding of
            complex information. Data art is a powerful medium for storytelling, going past the basic presentation of
            numbers through charts to create stories that connect with the audience. Using data analysis alongside
            artistic and narrative techniques, data art can convey insights, make arguments, and engage with its
            audience on a deeper level than a simple graph or chart.
            </p>

            <p>
            Some of the more interesting pieces of data art are ones you can interact with. Using different web
            technologies, like open graphics library (openGL) or ThreeJS, an artist can utilize the hardware on the
            device to create 3D visualizations. Using JavaScript, a coding language that runs on your browser, artists
            can “draw” all sorts of interactive media, creating unique experiences unlike any other medium.
            </p>

            <h2>A selfless society</h2>
            <span class="text-gray-500 space-y-0 mt-0">Dr. Julie Freeman</span>
            <p>
            The abstract interactive art piece titled “A selfless Society” by Dr. Julie Freeman, uses 3D openGL
            technologies to abstractly represent a colony of naked mole rats named Colony Omega that ran from 2016 to
            2020. These mole rats had tags embedded within their skin, and the tags would be tracked by sensors placed
            within their enclosure. Their movement data was tracked and used to move the shapes within the animation.
            The sounds were recorded noises made by the mole rats and played back within the animation. Since the
            project has shut down, the data used by the animation is recycled from when the colony was active. This
            animation is a unique way to represent animal behavioral data without showing the animals directly.
            In this animation, the mole rats’ movements become an unseen dance, choreographed by nature and
            captured through technology, offering a glimpse into their hidden world without ever laying eyes on the
            dancers themselves. It’s a poignant reminder of the unseen rhythms that govern all life,
            rendered visible by the art of data. <Cite citation={12}/>
            </p>
            <a href="http://rat.systems/selfless-society/" type="external" class="btn variant-filled-tertiary">
                View "A Selfless Society
            </a>


            <h2>They Rule</h2>
            <span class="text-gray-500 space-y-0 mt-0">Josh On</span>
            <p>
            The They Rule interactive piece is a commentary on the interconnected web of board of director members who
            sit in the largest 100 companies within the United States of America. The visualization asks you to enter a
            director or company, and plots it on a map, allowing you to click and expand the connections showing either
            the directors of a company, or all of the different companies a director has sat upon. After a few minutes
            of expanding companies and directors, you find yourself within a huge web of the people making decisions
            within the US. The data is pulled from Wikidata, a knowledge base able to read by both humans and computers.
            They Rule aims to show just how interconnected the people who run the top companies within the US. There is
            an option to include datasets from US presidents administrations, allowing you to actively visualize the
            connections and biases that the rules of the country have to these companies. “They Rule” serves as a digital
            magnifying glass, bringing into focus the dense network of influence and power held by a select few within
            the corporate sphere. It’s a visual exploration of the ties that bind the boardrooms of America’s corporate
            giants, revealing a complex lattice of leadership that shapes the nation’s economic landscape. <Cite citation={[11, 13]}/>
            </p>
            <a href="https://theyrule.net/" type="external" class="btn variant-filled-tertiary">
                View "They Rule"
            </a>

            <h2 class="space-y-0 mb-0">The Youtube & Twitch Atlas</h2>
            <span class="text-gray-500 space-y-0 mt-0">Kiran Gershenfeld</span>

            <h3>The Twitch Atlas</h3>
            <p>
            The Twitch Atlas is a map of the top channels on Twitch.tv, a gaming live streaming platform, and their
            overlap of shared “chatters,” viewers who talk in live streamers chats. Each node on the map is a Twitch
            streamer, and every line connecting them is at least 1000 shared chatters who chat in both channels. The
            size of each node is dependent on the number of unique viewers of the stream. Colors and placement of the
            bubbles are determined by an algorithm that detects “communities” of streamers who share large amounts of
            viewers. <Cite citation={14}/>
            </p>
            <h3>The Youtube Atlas</h3>
            <p>
            The Youtube Atlas is much the same as its Twitch counterpart, representing Youtube channels, their
            size, shared commenters, and shared viewers or communities using the nodes, node size, lines, and colour.
            The connection threshold is set at 350 commenters because, unlike the ephemeral nature of Twitch chats that
            merge into a swiftly flowing stream of messages, comments on a YouTube video create a lasting imprint,
            contributing to the video’s enduring legacy. These maps allow for a visual representation of the communities
            that arise on these platforms. Many of the communities that are isolated are language dependent and have
            shared creators who speak those languages, usually with one or two channels on the outskirts who bridge the
            gap and receive viewership from multilingual viewers.
            The Twitch Atlas and Youtube Atlas act as digital cartographers, charting the vast landscapes of social
            interaction within the gaming and video-sharing cosmos. They reveal not just the size and reach of digital
            content creators, but the intricate web of viewer relationships that form the backbone of these online
            communities. Koblin’s visualization captures the pulse of a nation on the move, reflecting the ebb and flow
            of daily life as seen through the skies. It’s a digital tapestry that weaves together time, space, and
            technology, showcasing the intricate dance of air travel. <Cite citation={14}/>
            </p>
            <div class="flex flex-row">
            <a href="https://twitchatlas.com/" type="external" class="btn variant-filled-tertiary mr-2">
                View "Twitch Atlas"
            </a>
            <a href="https://youtubeatlas.com/" type="external" class="btn variant-filled-tertiary ml-2">
                View "Youtube Atlas"
            </a>
            </div>
            <h3>Flights / flight paths visualized</h3>
            <span class="text-gray-500 space-y-0 mt-0">Aaron Koblin</span>
            <p>
            24 hours of flights in Flight Patterns Color
            Koblin uses live flight data from incoming and outgoing flights in the United States of America during a 24
            hour time period in 2008. Using the public data acquired from the Federal Aviation Administration (FAA),
            Koblin visually represents the location and altitude of the individual flights using colored trails. He
            created the animation by programmatically requesting the data from the FAA every 5 minutes, and had the
            program output a frame representing the data, he then compiled each frame in a video editing software.
            The final video is extremely engaging and relaxing to watch. The sight of planes sketching the contours of
            the United States, as they shuttle between major hubs, paints a vivid picture of the nation’s bustling activity.
            Observing how the time of day dictates flight patterns is intriguing; in the wee hours of 1 - 6 am EST, the
            skies clear as flight points dwindle to a whisper. Koblin’s visualization captures the pulse of a nation on
            the move, reflecting the ebb and flow of daily life as seen through the skies. It’s a digital tapestry that
            weaves together time, space, and technology, showcasing the intricate ballet of air travel. <Cite citation={15}/>
            </p>
            <a href="https://youtu.be/ystkKXzt9Wk?si=YZYqXxrajAmJ78DW" type="external" class="btn variant-filled-tertiary">
                Watch "Flight Patterns Color"
            </a>

        </div>
    </div>
</main>