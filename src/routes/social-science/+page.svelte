<script>
    import Carousel from "./Carousel.svelte";
    import Cite from "$lib/components/Cite.svelte";
</script>

<main>
    <div class="container h-full mx-auto flex justify-center items-center md:w-1/2">
        <div class="space-y-5 mt-5">

            <h1>Computational Social Science</h1>

            <p>Computational social science is an interdisciplinary field combining approaches for data collection,
                processing and modeling from computer science and data science and applying them to topics from the
                social sciences. This includes studies like computational economics, computational sociology,
                culturomics, cliodynamics, social media analysis.</p>

            <p>The behaviours of social science can be tracked and predicted by leveraging large data sets. This data
                can be acquired from a variety of sources, like from social media companies, public databases, web
                scraping and mobile phone data.</p>

            <h2>Data Collection</h2>
            <h3>Public Databases:</h3>
            <h4>historical data:</h4>
            <ul>
                <li>Seshat: Global History Databank, accounts the social and political organization of groups of
                    humans.
                </li>
                <li>Human Relations Area Files, World culture and Archaeology.</li>
                <li>Database of Places, Languages, Culture, and Environment (D-PLACE).</li>
                <li>The Atlas of Cultural Evolution, Archaeology.</li>
                <li>The Collaborative Information for Historical Analysis (CHIA), links academic and research
                    institutions
                    across the world and provides data on human social affairs.
                </li>
            </ul>
            <h4>Other databases:</h4>
            <ul>
                <li>Google books + Ngram viewer, A database for books and other printed media scanned using optical
                    recognition. Ngram allows for searches of strings and provides relevancy and usage trends.
                </li>
                <li>Linguistic Data Consortium, provides data on speech and text, for linguistic based research and
                    development.
                </li>
            </ul>
            <h3>Other sources:</h3>
            <p>
                Social networking companies like X corp., Alphabet, and Meta have users interact with their products <br>
                like X / Twitter, Google, Youtube, Facebook, and Instagram. These big data databases grow at extreme rates due
                to users interacting with them daily. Using Application Programming Interfaces (API), researchers are able
                to access and query the data. These APIs allow for companies to expose parts of their databases to the
                public without exposing sensitive data for the user.
            </p>

            <p>
                Web Scraping is a process where robots act like a user, requesting and viewing the pages we look at,
                they then look through the webpage and pull important information from the site and store them into a
                database, these processes are used when apis are unavailable or too restrictive. The resulting data is available
                for usage.
            </p>

            <h5>Talk about social science aspects</h5>

            <h2>Case studies</h2>
            <h4>Case 1:</h4>
            <p>
                During the covid-19 pandemic, google and apple worked together to create an exposure notification API, this
            allowed for developers and countries to create mobile phone applications that allowed for users to receive
            an early warning for potential covid-19 exposures. This system allowed for phones to connect to other phones
            using bluetooth and exchange a randomly generated code that lasts 20 minutes with each other. When an
            infection occurred, infected codes would be broadcast to other phones, which would then check if they had
            exchanged codes with the infected device. This process allowed for an early warning system that didn't
            expose users' data. <Cite citation={[2, 3]}/> The exposure notifications used a computational approach to model and track the
            spread of the spread of covid-19 through our social society. This system used large amounts of data in the
            forms of random keys, to calculate and track a question that was going through everyone's minds during the
                pandemic, “Have I been infected by someone?”
            </p>

            <h3>Twitter analysis process</h3>
            <p>
            Micro blogging social media sites like X / Twitter allow for people across the globe to quickly share ideas
            and opinions through short sentences, images, and videos. This allows for large amounts of dated, documented
            responses to topics to be recorded. These responses can be queried, filtered, sorted, and analyzed for
            various purposes. Entities can use the data resulting from analysis to understand the sentiments, behaviors,
            and responses of audiences.
            </p>

            <h5>Pipeline diagram</h5>

            <h4>Case 2:</h4>
            <p>
            Researchers used Twitter to understand the frequency of discussion over different scientific topics in 2017.
            Using the twitter API, these researchers were able to receive tweets as they users tweeted them, during the
            collection period, they received around 306 000 tweets. After filtering tweets not made by people, the
            number dropped to 219 000 tweets containing keywords about one of the scientific topics, with 50% of
            filtered tweets being a “retweet,” a reblogging of an original tweet. Most discussed topics were
            Neuroscience, Genomics and Biotechnology. These tweets were geolocated either by using the geolocation tag
            from the tweet itself, or from the profiles geolocation. The scientific tweets geolocation were plotted onto
            a map of the world using a heatmap, and sorted by scientific topics. General tweets were also plotted onto a
            heatmap for comparison as a control. <Cite citation={4}/> This study applied techniques employed by computational social
            scientists to retrieve and categorize a large data set, and used it to study social phenomena. The researches used
            techniques from sociology...
            </p>

            <Carousel
                    imgNames={['Science', 'Categorized', 'All']}
                    beforeAlt="A heatmap of the "
                    afterAlt=" tweets across the world."
                    afterPath=" heatmap.png"
                    title={true}
            />
            <span class="text-gray-500">1. Scientific Tweets, 2. Categorized Scientific Tweets, 3. All tweets</span>

            <h4>Case 3:</h4>
            <p>
            In 2012, Twitter was used to understand the mood of United Kingdom citizens between July 2009 and January
            2012. Over 484 million tweets were collected during the 31 month period using the Twitter API. The resulting
            set was used to sort tweets into lists containing words of anger, fear, joy or sadness for each day during
            the period with the frequency of the word corresponding to a higher value. Each day had a score for each
            category, which was graphed out. Two significant events occurred during the period of study, the 2010 budget
            cuts, which attempted to deal with the current recession. The other major event to occur during the period
            were riots that broke out on August 6th 2011. <Cite citation={5}/>
            </p>

            <Carousel
                imgNames={['Anger', 'Fear', 'Joy', 'Sadness']}
                beforeAlt="A map of the resulting "
                afterAlt=" emotion levels across the UK."
                afterPath=" Graph.png"
            />

            <p>
            Events like Halloween, Christmas, Valentines day, and Easter all have noticeable repeatable “multiplicative”
            effects to the raw value on each graph each year. Christmas was able to lower the levels of anger, fear, and
            sadness by a mostly consistent amount. During the 2010 year, after the budget cuts, the level of sadness
            within the country was extremely high and while Christmas was able to lower it by roughly the same amount as
            other years, it was not to the same level. Studying the emotional data provided by tweets during these time
            periods is an effective way to understand the sentiments shared by UK residents. <Cite citation={5}/>
            </p>
        </div>
    </div>
</main>

