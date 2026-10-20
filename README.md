# Wrapper-First Startup Ideas

Oct 20, 2026 · @Someone

> **Living document, not a finished report.** This doc will keep being updated. Anyone reading it is welcome to contribute: add your own ideas as new rows in the Idea list table, or leave comments. Use the approach described here as a starting point and build on it.

## TL;DR

The wrapper-first plan works as a cheap demand test, with three fixes covered in the conclusion.

**Top 5 ideas from this report:** a document and letter explainer in Indian languages, an English-speaking practice coach on real-time voice, a vernacular homework helper with voice explanations, an Indian-food calorie tracker, and creator dubbing into Indian languages. Virtual try-on for ethnic wear is the high-upside wildcard.

## The thesis

Big AI providers ship powerful capabilities as minor features inside bigger products, and most people never find them. A startup can unbundle one such feature, package it for a specific audience, and market it hard.

**Worked example of the core idea:** "find me this outfit." A user uploads a reference photo or types a look in plain English, and the app returns matching products across retailers. Google Lens already does a version of this. Most shoppers don't know it, and Lens isn't tuned to their stores, budget or style.

The staged plan:

1. **Wrapper MVP (weeks 1–4).** Glue existing APIs together behind a focused UI. No custom models. The only goal is to learn whether people use it and come back.
2. **Traction proof (months 1–3).** Retention, organic sharing, and early revenue or affiliate clicks. This is what investors actually look at.
3. **Raise.** Pitch the demand, the audience and the data you are collecting. Don't pitch the model.
4. **Own the stack (post-funding).** Replace API calls with your own retrieval, ranking or fine-tuned models where it cuts cost or improves quality. Optimization comes last, once you know what to optimize.

The logic is sound. Most consumer AI hits started this way, and building your own models before proving demand is the more common way to fail.

## Pressure test: where the thesis holds and where it breaks

The thesis holds for testing demand. It breaks in four places if you take it literally.

| Assumption | Reality (Oct 2026) | What to do |
| --- | --- | --- |
| "Wrap Google Lens" | No official Lens API exists. SerpApi and similar services scrape it, and [Google sued SerpApi in Dec 2025](https://www.computerworld.com/article/4110587/google-sues-data-scraping-company.html). | Rebuild the capability from official parts: Gemini vision to describe the item, multimodal embeddings to match it against an affiliate catalog. That takes about as long and won't get cut off. |
| "Investors fund the MVP" | Q1 2026 was a record funding quarter, but thin wrappers got [almost none of it](https://www.startupspotlight.org/p/the-wrappers-got-zero-follow-the). One advisory firm estimates wrapper funding fell from $4.2B (Q3 2024) to $1.3B (Q1 2026); [treat as indicative](https://beyondelevation.com/insights/are-ai-wrappers-fundable-2026). | Raise on retention, revenue and a data or distribution story. The wrapper is how you got there, not what you are selling. |
| "Users will discover us" | The underused feature is underused partly because discovery is hard for everyone, you included. | Choose ideas with a built-in channel: WhatsApp forwards, creator content, a shareable output (try-on images, dubbed videos). |
| "Optimize later" | The provider can ship your feature for free. Google already launched [Doppl](https://labs.google/doppl), a standalone try-on app, and try-on inside AI Mode shopping. | Pick a wedge the giant won't prioritize: Indian languages, ethnic wear, local catalogs, offline-first users, B2B for small sellers. |

**The case for the thesis is still strong.** [Cal AI](https://letsdatascience.com/news/cal-ai-sells-to-myfitnesspal-after-rapid-growth-f789c949), built by two high schoolers around photo calorie estimation, reached about $30–40M in annual revenue and 15M+ downloads before MyFitnessPal acquired it in 2026. The [top 50 consumer AI apps by revenue](https://officechai.com/ai/top-consumer-apps-by-revenue/) include many single-feature apps: Photoroom (background removal), Speechify (read aloud), Moises (song stem splitting), Topview (product link to video ad), Otter (meeting notes).

The real lesson: **a wrapper can be a business without VC.** Plan for revenue first, and treat funding as optional fuel.

## The idea-finding method

Your approach of unbundling a buried feature into its own app becomes a repeatable process if you add a demand filter and an access filter.

1. **Mine the feature lists.** Look at provider changelogs (the [Gemini API changelog](https://ai.google.dev/gemini/docs/changelog) shipped 40+ capabilities in 2026), Google Labs experiments, "N ways to use Lens" posts on [Google's blog](https://blog.google/products-and-platforms/devices/google-lens/google-lens-features/), and OpenAI and Apple release notes.
2. **Find the job-to-be-done.** Each feature should map to a sentence a normal person would type, like "what's this rash" or "translate this letter for my mom." If you can't write that sentence, drop the feature.
3. **Check for latent demand.** YouTube and Instagram tutorials that teach people a hidden feature are the strongest signal: people want it and can't find it. Reddit questions and Google Trends help too.
4. **Confirm official API access.** It must be commercially licensed and priced so a free tier is affordable. No scraping.
5. **Pick the wedge the giant won't serve.** A language, a region, a catalog, a profession, or a channel (WhatsApp, voice-first).
6. **Fake-door test before building.** Post a landing page or demo reel, run about ₹5–10K of ads or creator posts, and measure signups.
7. **Ship the MVP in 2–4 weeks** and judge it on week-4 retention and willingness to pay.

One addition to your approach: **the best unbundled features produce a shareable output** (an image, video, audio or a WhatsApp forward). That output solves the discovery problem for you.

## Raw material: capabilities you can wrap today

Each capability below sits buried in a consumer product but is available through an official API. Release dates are from the [Gemini API changelog](https://ai.google.dev/gemini/docs/changelog) and [Sarvam pricing](https://docs.sarvam.ai/api/pricing.md).

| Capability | Where it hides today | Official API to build on | Cost / status note |
| --- | --- | --- | --- |
| Visual search ("find this item") | Google Lens, Circle to Search | Gemini vision + `gemini-embedding-2` multimodal embeddings (GA Apr 2026) over your own catalog | Pennies per search. Catalog comes from affiliate feeds. |
| Virtual try-on | Google Shopping, Doppl app | [Vertex AI Virtual Try-On](https://docs.cloud.google.com/vertex-ai/generative-ai/docs/image/generate-virtual-try-on-images) (`virtual-try-on-001`) | Takes a person photo plus a garment photo and returns up to 4 images. Check current pricing. |
| Conversational image editing | Gemini app (Nano Banana) | Nano Banana 2 GA May 2026; 2.1 GA Oct 2026 | Character consistency across edits |
| Place and dish lookup | Lens "near me", Maps | Grounding with Google Maps (extended to Gemini 3, Mar 2026) | Billed per grounded request |
| Real-time voice conversation | Gemini Live | Live API (Gemini 3.8 Live GA Sep 2026) | Audio-to-audio, low latency |
| Voice design and TTS | Gemini app, NotebookLM | Gemini 3.8 Flash TTS (GA Sep 2026), 150+ voices | Multi-speaker "podcast" style output |
| Long-video understanding | YouTube "Ask", Gemini | Agentic video understanding (Sep 2026) | Up to 88% fewer tokens on long video, per Google |
| Short video generation | Gemini app, Flow | Veo 3.1 Lite, Gemini Omni Flash (GA Aug 2026) | Lowest-cost tiers suit ad creatives |
| Music generation | Flow Music | Lyria 3.5 (GA Sep 2026) | Full-length songs |
| Computer use (agent clicks through sites) | Gemini agent features | Computer Use tool (preview) | Preview only. High ToS risk on target sites. |
| Indian-language speech and translation | Google Translate, YouTube auto-dub | Sarvam: STT ₹30/hr, TTS ₹30 per 10K chars, translate ₹20 per 10K chars | ₹100 free credit |
| Document reading (Indic) | Lens "text" mode | Sarvam Document Intelligence ₹0.5–1 per page | Max 10 pages per job |
| Video dubbing (Indic) | YouTube auto-dubbing | Sarvam Dubbing ₹36–40 per source minute | Per target language |

The Indian-language column matters most. Google and OpenAI support Hindi or Tamil, but they rarely market to those users as a first-class audience. That gap is your wedge.

## Idea list

These 16 ideas each unbundle one capability from the table above. Most assume an India-first launch, since that is where the big providers under-market.

| # | Idea | User and job | Built on | MVP (2–4 weeks) | Wedge and money | Main risk |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | **Letter and document explainer** | "Explain this bank notice, insurance policy, rent agreement or govt letter to my parents, in Hindi" | Sarvam Document Intelligence + Gemini + Sarvam TTS | WhatsApp bot: send a photo, get a plain-language voice note plus a 3-line summary | Elderly and first-time users via family WhatsApp forwards. Freemium; B2B for banks and insurers later. | Wrong explanation of a legal or financial term. Needs disclaimers. |
| 2 | **English-speaking practice coach** | "I freeze in interviews and calls in English" | Gemini Live API (real-time voice) | App with 10 role-play scenarios (interview, customer call, HR round) and feedback after each | Huge "spoken English" market in India. ₹199–499/month. [Jumpspeak](https://officechai.com/ai/top-consumer-apps-by-revenue/) proves the format. | Voice API cost per minute. Cap free minutes. |
| 3 | **Virtual try-on for ethnic wear** | "How will this saree or lehenga look on me?" | Vertex AI Virtual Try-On + Nano Banana editing | Web app: upload a selfie and paste a product link or image to get try-on photos | Wedding shoppers; B2B plug-in for Instagram and D2C sellers. Shareable images drive growth. | Draped garments may render poorly. Test quality first. Google could expand Doppl to India. |
| 4 | **"Find this dish or place" from a reel** | "Where can I eat this, or go here, near me?" | Gemini video and image understanding + Maps grounding | Share a reel or screenshot into the app, get the dish or place and the nearest options | Food and travel creators; affiliate fees from Zomato, Swiggy and booking sites | Maps grounding display and attribution rules. Weak retention unless you add saved lists. |
| 5 | **Vernacular homework helper** | "Explain this maths problem in Tamil, out loud, the way my teacher would" | Gemini vision + Sarvam TTS | Snap a question, get a step-by-step answer plus a voice explanation, aligned to CBSE and state boards | Tier-2/3 students and parents; ₹99/month. Gauth and Photomath are English-first. | Accuracy on board-specific syllabi; cheating backlash |
| 6 | **Shop-the-look outfit finder** (your core idea) | "Find me this outfit, under ₹2,000, on Myntra or Ajio" | Gemini vision + `gemini-embedding-2` over affiliate catalogs | Upload a photo or describe a look, get ranked matches with affiliate links | Gen Z on Instagram; affiliate commission | Catalog freshness. Others are already doing it, so differentiate on price filter or style. |
| 7 | **Indian thali calorie tracker** | "Log my lunch by photo, including dal, roti and sabzi" | Gemini vision | Photo to calories and macros, tuned for Indian dishes and portion sizes | Proven model ([Cal AI](https://letsdatascience.com/news/cal-ai-sells-to-myfitnesspal-after-rapid-growth-f789c949)); Indian food is its weak spot. Subscription. | Crowded category; estimate accuracy |
| 8 | **Creator dubbing into Indian languages** | "Put my YouTube course out in Hindi, Telugu and Bengali" | Sarvam Dubbing + Gemini for translation review | Upload a video, get dubbed versions, with an editor to fix lines | Edtech and regional creators. Charge per minute at a markup over ₹36–40. | YouTube's built-in auto-dub could improve. Lip-sync expectations. |
| 9 | **Product link to video ad** | "Make a 15-second Reel ad for my Meesho product" | Veo 3.1 Lite or Omni Flash + TTS | Paste a link, get 3 ad variants with a vernacular voiceover | Small online sellers. Per-video credits. [Topview](https://officechai.com/ai/top-consumer-apps-by-revenue/) proves demand. | Generated-video quality; ad-platform policies |
| 10 | **Notes to study podcast** | "Turn my semester notes into a 10-minute Hinglish podcast" | Gemini + multi-speaker TTS (a NotebookLM-style audio overview) | Upload a PDF, get a two-host audio episode and a quiz | College students; exam-season spikes | NotebookLM is free and improving |
| 11 | **Home decor redesign and shop** | "Show my room in Scandinavian style, then let me buy those pieces" | Nano Banana editing + embeddings over furniture catalogs | Upload a room photo, pick a style, get a redesign with matched products | New-home buyers and renters; affiliate commission | Matching generated items to real products is hard |
| 12 | **Crop and plant problem helper** | "What's wrong with my tomato leaves?" in Marathi voice | Gemini vision + Sarvam STT/TTS | WhatsApp bot: photo plus voice question, voice answer | Farmers via FPOs and agri-input sellers (B2B2C) | Plantix exists; rural monetization is hard |
| 13 | **Old photo restore and animate** | "Restore my grandparents' photo and make it move" | Nano Banana editing + Veo image-to-video | Upload a photo, get restored and animated versions | Festival and wedding moments; viral sharing; credits | Novelty fades. Retention is weak. |
| 14 | **Shopkeeper voice ledger** | "Record udhaar (credit) and stock by voice note" | Sarvam STT + Gemini for structuring | WhatsApp voice note, get a ledger entry and a daily summary | Kirana stores; ₹ per month | Khatabook and OkCredit own the category; switching cost |
| 15 | **Lecture and video summarizer for exams** | "Summarize these 40 hours of UPSC lectures into notes" | Gemini agentic video understanding | Paste a playlist, get structured notes and flashcards | Competitive-exam aspirants; subscription | Copyright on paid course content |
| 16 | **Song practice and karaoke** | "Remove vocals so I can practise this Bollywood song" | Stem separation (open models such as Demucs) + Lyria for backing tracks | Upload a song, get an instrumental, pitch shift and lyrics sync | Music learners; [Moises](https://officechai.com/ai/top-consumer-apps-by-revenue/) proves demand | Music licensing and copyright |

One more to watch, not build yet: **agentic form filling** (Tatkal tickets, government portals) with the Computer Use tool. Demand is enormous, but it is preview-only and breaks most target sites' terms.

## Scoring and shortlist

The document explainer and the English-speaking coach score highest: proven demand, a weekend-sized build, and a wedge Google and OpenAI aren't chasing. Scores are my judgment from the research above, each 1–5 where 5 is best (platform safety 5 means least likely to be copied by the provider).

| # | Idea | Demand | Will pay | Build speed | API ready | Moat path | Platform safety | Total /30 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Letter and document explainer | 4 | 3 | 5 | 5 | 4 | 4 | **25** |
| 2 | English-speaking practice coach | 5 | 4 | 4 | 5 | 3 | 3 | **24** |
| 5 | Vernacular homework helper | 5 | 3 | 4 | 5 | 3 | 3 | **23** |
| 7 | Indian thali calorie tracker | 4 | 4 | 5 | 5 | 2 | 2 | **22** |
| 8 | Creator dubbing into Indian languages | 4 | 4 | 4 | 5 | 3 | 2 | **22** |
| 3 | Virtual try-on for ethnic wear | 4 | 3 | 4 | 3 | 4 | 3 | **21** |
| 9 | Product link to video ad | 4 | 4 | 4 | 4 | 2 | 2 | 20 |
| 12 | Crop and plant problem helper | 3 | 1 | 4 | 5 | 3 | 4 | 20 |
| 15 | Lecture and video summarizer | 4 | 3 | 4 | 4 | 2 | 3 | 20 |
| 4 | "Find this dish or place" from a reel | 3 | 2 | 4 | 4 | 3 | 3 | 19 |
| 13 | Old photo restore and animate | 3 | 2 | 5 | 5 | 1 | 3 | 19 |
| 6 | Shop-the-look outfit finder | 4 | 2 | 3 | 4 | 3 | 2 | 18 |
| 11 | Home decor redesign and shop | 3 | 2 | 3 | 4 | 3 | 3 | 18 |
| 14 | Shopkeeper voice ledger | 3 | 2 | 4 | 5 | 2 | 2 | 18 |
| 10 | Notes to study podcast | 3 | 2 | 5 | 5 | 1 | 1 | 17 |
| 16 | Song practice and karaoke | 3 | 3 | 4 | 3 | 2 | 2 | 17 |

Two patterns stand out. Ideas that combine **Indian languages with a voice or WhatsApp interface** score best on platform safety. Pure image-generation novelties (photo restore, study podcasts) are fast to build but have no moat. Try-on scores lower on API readiness only because draped garments need a quality test before you commit.

## MVP-to-funding playbook: the first 90 days

The goal by day 90 is a retention curve that flattens and early revenue. That evidence is enough to raise, or to keep growing without raising.

1. **Days 1–7: fake-door test 3 ideas.** One landing page and one 20-second demo video per idea. Spend about ₹5–10K on Instagram ads or creator posts per idea. Keep the idea with the best signup rate.
2. **Days 8–30: wrapper MVP.** Use API calls only: Gemini, Sarvam, Vertex. Ship on WhatsApp or as a PWA before native apps. Log every input, output and user correction from day one; that log becomes your data moat.
3. **Days 31–60: find the retention signal.** Track week-1 and week-4 retention, shares per user, and cost per active user. Add a paywall or affiliate links early to test willingness to pay.
4. **Days 61–90: build the story.** If week-4 retention is above roughly 20% and unit economics work at your price, pitch. The pitch is the audience, growth curve, proprietary dataset and channel. The API is a detail.
5. **Post-funding: own the stack.** Replace the most expensive or lowest-quality API step first, using the data you logged: fine-tune a small open model, build your own retrieval index, or negotiate volume pricing.

**Kill criteria:** a week-4 retention under 10%, or a per-user API cost above what users will pay. Either one means you move to the next idea on the shortlist. Don't optimize a product nobody returns to.

## Conclusion: three fixes before you build

The wrapper-first plan works as a cheap demand test, but it needs three fixes before you build on it.

1. **Wrap official APIs, not consumer products.** Google Lens has no official API. The popular "Lens API" from SerpApi works by scraping, and Google sued SerpApi in December 2025. Build on Gemini vision, multimodal embeddings, Vertex AI Virtual Try-On, Maps grounding, and Indic APIs like Sarvam.
2. **Raise on traction, not the wrapper.** VC money for thin "ChatGPT-for-X" apps has dried up in 2026. Single-feature consumer apps still make real revenue, though: Cal AI (photo calorie counting) reached roughly $30–40M a year and was bought by MyFitnessPal.
3. **Start collecting your moat on day one.** That means proprietary catalog mappings, user preference data, vernacular language, or a distribution channel (WhatsApp, creators) that the big provider won't serve.

## Sources

- [Gemini API release notes (2026)](https://ai.google.dev/gemini/docs/changelog)
- [Vertex AI Virtual Try-On docs](https://docs.cloud.google.com/vertex-ai/generative-ai/docs/image/generate-virtual-try-on-images)
- [Sarvam AI API pricing](https://docs.sarvam.ai/api/pricing.md)
- [SerpApi: "Google doesn't have an official API for Google Lens"](https://serpapi.com/blog/building-an-image-based-search-app-with-google-lens-api/)
- [Computerworld: Google sues data scraping company SerpApi](https://www.computerworld.com/article/4110587/google-sues-data-scraping-company.html)
- [Google blog: 8 ways Google Lens can help](https://blog.google/products-and-platforms/devices/google-lens/google-lens-features/)
- [Google Doppl](https://labs.google/doppl)
- [Google Labs experiments overview](https://www.hashtagtreinamentos.com/google-labs-ai)
- [Startup Spotlight: Q1 2026 and AI wrapper funding](https://www.startupspotlight.org/p/the-wrappers-got-zero-follow-the)
- [Beyond Elevation: are AI wrappers fundable in 2026](https://beyondelevation.com/insights/are-ai-wrappers-fundable-2026) (marketing content; figures unsourced)
- [Cal AI sells to MyFitnessPal](https://letsdatascience.com/news/cal-ai-sells-to-myfitnesspal-after-rapid-growth-f789c949)
- [Top 50 consumer AI apps by revenue, Oct 2026](https://officechai.com/ai/top-consumer-apps-by-revenue/)
