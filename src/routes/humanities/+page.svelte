<script lang="ts">
    import type {PageData} from './$types';
    import Cite from "$lib/components/Cite.svelte";

    export let data: PageData;
</script>

<main>
    <div class="container h-full mx-auto flex justify-center items-center md:w-1/2">
        <div class="space-y-5 mt-5">
            <h1>Computational Linguistics</h1>
            <p>
            Computational Linguistics is a field that combines practices and theories from linguistics with models and
            algorithms from computer science that aims to allow computers to understand and replicate human language.
            Computational linguistics and Natural language processing (NLP) is the study of solving the problems that
            arise during the interpretation or generation of human language through either text or speech. Computational
            linguistics is split into two categories, methods involving text / written language, and methods involving
            speech. <Cite citation={6}/>
            </p>

            <h2>Types of linguistic analysis</h2>
            <h3>Audio Analysis</h3>
            <p>Speech recognition involves matching phonetics and waveforms to a dictionary of matching phonetics
                to build text from speech.</p>

            <h3>Text Analysis</h3>
            <p>
            Text analysis revolves around splitting chunks of text or strings into tokens. These tokens then get tagged
            for different part-of-speech (POS tagging), like nouns, verbs, adjectives and punctuation. There are
            different datasets for matching these tokens, some have been generalized for any type of text, some are
            focused on academics, others have focused on social media. There is a process called Entity linking (EL) or
            Named Entity Recognition which recognizes a name of a person, place, organization, location, etc. These link
            the words to a database of information that allows for outside information to be available to the processor.
            After POS tagging and EL, tokens are then grouped into either verb or noun groups. After these processing
            steps are done, traditionally math and statistics was used to pull the information from these strings, but
            recently neural networks trained on huge datasets have been able to outperform the traditional methods in
            extracting the information from these strings. <Cite citation={[6, 7]}/>
            </p>

            <h2>Linguistic Technologies</h2>
            <p>Advancements within this field has led to many new tools and innovations, (talk about disabilities n stuff)</p>
            <ul>
             <li>
                translators
             </li>
                <li>
                sentiment analysis
                </li>
                <li>
                speech recognition
                </li>
                <li>
                 Chat bots and text generators
                </li>
                <li>
                information extraction / text summarization
                </li>
                <li>
                    Natural language interfaces: These interfaces allow for humans to interact with software using
                    natural language or spoken words instead of a visual user interface. This technology is used in
                    virtual assistants like Siri, Alexa, and Google Assistant.
                </li>
            </ul>


            <h2>Artificial Innovation</h2>
            <p>
            The field of computational linguistics has been revolutionized by the advancements in Artificial
            Intelligence (AI) and machine learning. The areas of neural networks and deep learning have advanced rapidly
            within the last few years, these technologies have brought vast improvements to the accuracy and efficiency
            of natural language processing tasks.
            </p>
            <ul>
                <li>
                Neural Networks: Neural networks are systems inspired by the human brain. They consist of layers of
                connected nodes, or “neurons.” These networks “learn” from data by adjusting connections between these
                nodes. In computational linguistics, neural networks have been used to create vastly more accurate models
                for tasks such as POS tagging and Entity Linking. <Cite citation={8}/>
                </li>
                <li>
                Deep Learning: Deep learning is a subset of machine learning that uses neural networks with vast amounts of
                nodes and layers - where the term ‘deep’ arises. Deep learning neural networks are able to learn from huge
                amounts of data and once “trained” are able to extract features from new raw input data, which is useful for
                tasks such as speech recognition and sentiment analysis. <Cite citation={[7, 8]}/>
                </li>
                <li>
                Transformers: The most significant advancement in machine learning recently has been the development of
                transformer models, like OpenAi’s GPT (Generative Pretrained Transformer). These models work in three parts,
                an encoder, a huge neural network, and an decoder. The encoder allows for the neural network to take in
                strings analyzed using Text Analysis while also focusing the attention on different parts of the input by
                using an attention mechanism. The input tokens get encoded and run through the neural network, transforming
                it into data for the decoder to turn back into tokens using probability. Transformers have led to huge
                improvements during tasks like machine translation and text summarization. <Cite citation={[7, 8, 9, 10]}/>
                </li>
                <li>
                Pretrained Language Models: Pretrained models like chatGPT and GPT-4 are trained on very large datasets of
                text data. ChatGPT was trained on 500 billion tokens, and GPT-4 was trained on 13 trillion tokens. After
                being trained, these models are able to do specific tasks without very much input data being required. This
                has created versatile models that can handle a large amount of language processing tasks that don't require
                extra training. <Cite citation={[9, 10]}/>
                </li>
            </ul>

            <h5>Maybe Neural Network Animation</h5>

            <h2>Linguistic Challenges</h2>
            <p>
                There are many challenges in computational linguistics as human language is inherently ambiguous. Words
                spelled the same can have different meanings, sentences can be interpreted in different ways depending on
                the context. The word “bank” could refer to the side of a river, or a financial institution. The sentence “I
                saw a man with a telescope” could mean that you saw someone while using a telescope, or you saw someone who
                had a telescope. Different languages and dialects can have their own unique structure, grammar, and
                vocabulary. Even within a single language, different dialects may use different vocabulary or structure
                their sentences differently. <Cite citation={6}/>
            </p>


        </div>
    </div>
</main>


<style>
    ul {
        @apply leading-loose ml-6;
        list-style-type: disc;

    }
</style>