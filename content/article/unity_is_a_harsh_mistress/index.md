---
title: "Unity is a harsh mistress 💔"
date: 2023-09-15
categories: ['Devblog']
tags: ['Devblog']
icon: "fa-newspaper"
showDate: false
categories: false
tags: false
featuredImage: "/Dawn-Of-The-Cards/images/unity_is_a_harsh_mistress/riccitiello.jpg"
---

![Unity](/Dawn-Of-The-Cards/images/unity_is_a_harsh_mistress/riccitiello.jpg "Unity")

A calm analysis of Unity's latest business plans and a conclusion.

<!--more-->

# What is going on?

If you use the Unity game development engine, you are probably aware of the radical, and controversial, change in their [pricing plans](https://blog.unity.com/news/plan-pricing-and-packaging-updates).

To summarize, they are the following points:

* The **'Unity Plus' plan will be discontinued**. Current subscribers will receive an offer to upgrade to the '**Unity Pro**' plan for **one year** at the '**Unity Plus**' price.
* Pricing plans will be '**Unity Personal**' (free[^1]), '**Unity Pro**' (~$2000/year/seat) and '**Unity Enterprise**' (?) (the '**Unity Industry**' plan is not mentioned).
* The '**Unity Runtime Fee**', a charge for each installation of the game billed monthly, is introduced.

[^1]: _Only if you earn less than $200,000 (net) per year._

# Unity Runtime Fee

The '**Unity Runtime Fee**' is a fee to be paid by the developer for each installation of his game made with Unity. **BOTH** conditions must be met for this to apply:

  * Your game exceeds a certain **number of installations**.
  * Your **net income** in the last twelve months exceeds a certain number.

Only when **both conditions** are met, this payment applies. And only for installations that exceed the limit number of installations. If you only exceed the limit in one installation, you would only pay for that extra installation.

The limit of installations depends on the plan you have:

  * '**Unity Personal**' and '**Unity Plus**': **200000**.
  * '**Unity Pro**' and '**Unity Enterprise**': **1000000**.

The same as the net income limit:

  * '**Unity Personal**' and '**Unity Plus**': **$200,000** (USD).
  * '**Unity Pro**' and '**Unity Enterprise**': **$1,000,000** (USD).

And finally, if you meet these two conditions, the price to pay for installation will depend on the country where it is installed. If it is **not from an '_emerging market_'**[^2]:

  * '**Unity Personal**' and '**Unity Plus**': **$0.20** (USD) per new install.
  * With '**Unity Pro**' will depend on each new installation, which exceeds the limit, per month:
    * 000001 - 100000: **$0.15** (USD) per new install.
    * 100001 - 500000: **$0.075** (USD) per new install.
    * 500001 - 1000000: **$0.03** (USD) per new install.
    * 1000001+: **$0.02** (USD) per new install.
  * With '**Unity Enterprise**', will depend on each new installation, which exceeds the limit, per month:
    * 000001 - 100000: **$0.125** (USD) per new install.
    * 100001 - 500000: **$0.06** (USD) per new install.
    * 500001 - 1000000: **$0.02** (USD) per new install.
    * 1000001+: **$0.01** (USD) per new install.

If the installation occurs in a '*emerging market*'[^2]:

  * '**Unity Personal**' and '**Unity Plus**': **$0.02** (USD) per new install.
  * '**Unity Pro**': **$0.01** (USD) per new install.
  * '**Unity Enterprise**': **$0.005** (USD) per new install.

Finally, some exceptions. The '**Unity Runtime Fee**' will not be paid for games that:

* Use WebGL or streaming.
* Games using gaming subscription services.
* Charity bundles.
* Reinstalls of the same game, on the same device (on different devices, **counts as a new installation**).
* Pirate installations or '_install bombing_' (how Unity will detect this is a mystery).
* Demos of games that do not have the complete content (_early access_ are not considered demos).
* Subscription-based games as Apple Arcade, Xbox Game Pass, PlayStation Plus, etc (Unity plans to be paid by the service?).

You are also eligible for a price reduction if you use Unity services such as '[Unity Gaming Services](https://unity.com/solutions/gaming-services)' or '[Unity LevelPlay](https://unity.com/unity-ads-ironsource)'.

[^2]: _According to Unity, these are **not emerging markets**: United States, Australia, Austria, Belgium, Canada, Denmark, Finland, France, Germany, Ireland, Japan, Netherlands, New Zealand, Norway, Sweden, Switzerland, South Korea, and the United Kingdom. All the rest are._

It's all very simple, isn't it? Now comes the **best part**...

# Retroactive

**Unity silently removed** their [GitHub repo](https://github.com/Unity-Technologies/TermsOfService) (404) to track license changes, then updated a **new license** to remove the clause that lets you use the TOS from the version you shipped with.

As of January 1 2024, **no matter what version** of Unity you make your game with, if you meet the requirements, you will have to pay the '**Unity Runtime Fee**'.

[Is this legal?](https://www.egdf.eu/egdf-unitys-install-fees-are-a-sign-of-looming-game-engine-market-failure/) I guess we will know very soon.

# Community reaction

![Fucked by Unity](/Dawn-Of-The-Cards/images/unity_is_a_harsh_mistress/fuckedbyunity.jpg "Fucked by Unity")

Thanks to poor communication from Unity, the majority reaction has been [total](https://garry.net/posts/unity-can-get-fucked) [rejection](https://twitter.com/FuckedByUnity), misinformation, calls for a [boycott](https://mobilegamer.biz/unity-boycott-begins-as-devs-switch-off-ads-to-force-a-runtime-fee-reversal/), calls for its CEO to resign, many [m](https://twitter.com/fronkongames/status/1701929824128770467)[e](https://twitter.com/fronkongames/status/1701933277236383763)[m](https://twitter.com/fronkongames/status/1702277729410785688)[e](https://twitter.com/fronkongames/status/1702360626536833108)[s](https://www.reddit.com/r/Unity3D/comments/16iz63g/goodbye_my_darling_you_were_taken_too_soon/), hatred and even [death threats](https://www.bloomberg.com/news/articles/2023-09-14/video-game-company-unity-closes-offices-following-death-threat)[^3].

[^3]: In the end, it seems that they were [false](https://www.polygon.com/23873727/unity-credible-death-threat-offices-closed-pricing-change).

It also did not help to know that its CEO [John Riccitiello](https://en.wikipedia.org/wiki/John_Riccitiello) sold, days before changing the payment plans, [2000 shares of Unity](https://finance.yahoo.com/news/unity-software-incs-president-ceo-050515124.html). Shares that today are worth -47% of their original [IPO](https://venturebeat.com/business/unity-technologies-raises-more-than-1-1-billion-in-ipo-at-12-1-billion-valuation/) value.

![Stocks](/Dawn-Of-The-Cards/images/unity_is_a_harsh_mistress/stocks.jpg "Stocks")

And not only the community is pissed, but also the Unity engineers, whose superiors don't seem to care much about what they think:

![Employee](/Dawn-Of-The-Cards/images/unity_is_a_harsh_mistress/employee.jpg "Employee")

# How it affects us

If you use Unity, the situation is worrying. But not for the reasons you think. The '**Unity Runtime Fee**' will negatively affect:

> # **Free games with a very low [ARPU](https://en.wikipedia.org/wiki/Average_revenue_per_user)**

Or to put it another way, F2P with only advertising revenue. Is it a coincidence that if you use '[Unity LevelPlay](https://unity.com/unity-ads-ironsource)' (formerly [Iron Source](https://unity.com/unity-ads-ironsource)), Unity's advertising service, you can receive a discount on '**Unity Runtime Fee**'? 🤔

Is this an attempt to kill [AppLovin](https://www.applovin.com/)? 🤔

Does it have anything to do with AppLovin trying to [buy Unity for $20 billion](https://www.cnbc.com/2022/09/12/applovin-abandons-effort-to-buy-unity-after-20-billion-bid-rejected.html)? 🤔

What does the CEO of AppLovin [think about this](https://www.applovin.com/blog/my-views-on-the-unity-price-change/)? 🤔

Whatever Unity's reasons are for this change, I really believe that the vast majority of developers will not be affected. For those that do, many will still pay less than if they were using [Unreal Engine](https://www.unrealengine.com/en-US/faq) (which has no royalties up to $1000000, after that you pay 5%).

Let's see it with these graphs[^4], first for using '**Unity Personal**' and '**Unity Plus**':

[^4]: [Source](https://blog.runevision.com/2023/09/charts-to-visualize-how-much-you-owe.html).

![Plus](/Dawn-Of-The-Cards/images/unity_is_a_harsh_mistress/plus.png "Plus")

And this one for '**Unity Pro**'.

![Pro](/Dawn-Of-The-Cards/images/unity_is_a_harsh_mistress/pro.png "Pro")

* Most of us are in the 0% zone (according to Unity about 90%) 🥲.
* If you earn more than $200,000 net, it makes sense for you to upgrade to the '**Unity Pro**' plan.
* If you are in the 0% to 5% zone, and you are not thinking about developing your own technology or using [open source alternatives](https://godotengine.org/), it is not worth changing if you are happy with Unity.
* If you are outside the above zones, evaluate the costs of migrating your technology or creating your own. Perhaps you should also evaluate your business model.

# My conclusions

![game](/Dawn-Of-The-Cards/images/dragging_and_dropping_3d_cards/promo.gif "game")

I have been using Unity [professionally](https://github.com/FronkonGames) since version 4. With Unity I have developed games for PC, mobile and consoles. I've been [selling assets in their store](https://assetstore.unity.com/publishers/62716) for almost 10 years.

I have co-founded several game companies and as CTO I have chosen Unity as our technology. I'm even [developing a game](https://fronkongames.github.io/Dawn-Of-The-Cards/) right now using Unity.

**I like Unity** for being able to use C#, the customization of its Editor, its asset store, the speed of prototyping and its huge community.

But I would say **Unity is a harsh mistress**, especially after its IPO. Let's take a look at this timeline:

* 2014: [John Riccitiello](https://en.wikipedia.org/wiki/John_Riccitiello) (ex-Electronic Arts) replaces [David Helgason](https://www.linkedin.com/in/davidhelgason/) as CEO of Unity.
  * Unity [acquired Playnomics](https://www.gamesindustry.biz/unity-acquires-playnomics-report).
  * Unity [adquired Everyplay](https://unity.com/our-company/newsroom/unity-technologies-acquire-applifier-bring-everyplay-social-gaming-community).
* 2017: Unity changes the way of naming versions. Unity 5.6 is renamed 2017. For me, version 2017.2 was the last good one.
* 2018: Unity goes public at $68 per share, today it is worth $36.
  * Unity presents its '[Scriptable Render Pipeline](https://docs.unity3d.com/Manual/ScriptableRenderPipeline.html)', with two flavors 'Lightweight Rendering Pipeline' (now renamed to '[Universal Render Pipeline](https://unity.com/srp/universal-render-pipeline)') and '[High-Definition Rendering Pipeline](https://unity.com/srp/High-Definition-Render-Pipeline)'. The [#SRPLife](https://forum.unity.com/threads/join-us-for-srplife-week.915275/) chaos begins and to this day it continues to give me nightmares.
  * Unity [acquired Digital Monarch Media](https://unity.com/our-company/newsroom/unity-technologies-acquire-digital-monarch-media-pioneer-next-generation-real).
  * Unity [introduces DOTS](https://www.youtube.com/watch?v=j4rWfPyf-hk), a data-oriented design tech, four years later version 1.0 is released.
* 2019: Unity [acquired Vivox](https://variety.com/2019/gaming/news/unity-technologies-acquires-vivox-1203122251/).
  * Unity [acquired deltaDNA](https://unity.com/our-company/newsroom/unity-technologies-acquires-deltadna-games-liveops-provider) for $53M.
  * Unity [acquired ChilliConnect](https://unity.com/our-company/newsroom/unity-technologies-acquires-chilliconnect).
  * Unity [acquired Obvioos](https://www.gamesindustry.biz/unity-acquires-cloud-video-streaming-service-creator-obvioos) for $123M.
* 2021: Unity [acquired Ziva Dynamics](https://www.marketscreener.com/quote/stock/UNITY-SOFTWARE-INC-112492634/news/Unity-Software-Inc-NYSE-U-acquired-Ziva-Dynamics-Inc-for-approximately-130-million-37636791/) for $130M.
  * Unity [acquired Parsec](https://techcrunch.com/2021/08/10/unity-to-acquire-parsec-in-its-biggest-acquisition-to-date/) for $320M.
  * Unity [acquired Weta Digital](https://investors.unity.com/news/news-details/2021/Unity-Completes-Acquisition-of-Weta-Digitals-Tools-Pipeline-and-Engineering-Talent/default.aspx) for $1.6B.
* 2020: Unity [acquired Artomatix](https://www.irishtimes.com/business/technology/artomatix-buyer-revealed-as-unity-technologies-1.4173915) for $60M, two years later it is discontinued.
  * Unity [acquired Finger Food Advanced](https://blog.unity.com/news/finger-food-advanced-technology-group-joins-unity) for $23M.
  * Unity [acquired Plastic SCM](https://mcvuk.com/development-news/unity-acquires-plastic-scm-developer-codice-software/).
  * Unity [acquired Codice Software](https://venturebeat.com/business/unity-acquires-codice-software-to-manage-3d-workflows/).
  * Unity [acquired RestAR](https://www.businesswire.com/news/home/20201215005325/en/Unity-Acquires-RestAR-to-Enable-AI-Based-3D-Capture).
  * Unity introduces [Visual Scripting](https://unity.com/features/unity-visual-scripting) (formerly Bolt).
  * Unity introduces [Barracuda](https://docs.unity3d.com/Packages/com.unity.barracuda@1.0/manual/index.html), a lightweight cross-platform neural network inference library. Three years later it was replaced by 'Sentis'.
* 2021: Unity [acquired PiXYZ](https://blog.unity.com/news/pixyz-software-joins-unity).
    * Unity [acquire SyncSketch](https://blog.unity.com/news/welcome-syncsketch) for $30M.
    * Unity [acquire VisualLive](https://blog.unity.com/news/visuallive-joins-unity).
* 2022: Unity cancels, and fires all involved, the ['Gigaya' project](https://blog.unity.com/games/introducing-unitys-latest-sample-game-gigaya), its first and only attempt to make a complete game.
  * Unity [buys ironSource](https://techcrunch.com/2022/11/07/unity-and-ironsources-4-4b-merger-is-now-complete/), formerly InstallCore, a giant malware producer, for $4.4B.
  * John Ricciatello said developers that shun monetisation practises or leave them to later in the development cycle are '[fucking idiots](https://www.gamesindustry.biz/riccitiello-developers-who-push-back-against-monetisation-are-pure-brilliant-and-fucking-idiots)'.
  * AppLovin offers $20B for Unity, but without ironSource. The deal is [rejected](https://www.cnbc.com/2022/09/12/applovin-abandons-effort-to-buy-unity-after-20-billion-bid-rejected.html).
  * Unity introduces '[Unity Gaming Services](https://unity.com/solutions/gaming-services)'.
  * Unity introduce '[UI Toolkit](https://unity.com/features/ui-toolkit)'.
  * Unity close '[Unity Answers](https://forum.unity.com/threads/unity-answers-shutdown-canceled.1293360/)'.
* 2022: Unity introduces '[Verified Solutions](https://unity.com/partners/verified-solutions)' in the store.
  * Unity introduce ['Muse' and 'Sentis'](https://blog.unity.com/engine-platform/introducing-unity-muse-and-unity-sentis-ai), AI-powered tools.
* 2023: Unity introduce ['Netcode for GameObjects'](https://unity.com/products/netcode).
  * Unity introduce '[Unity Runtime Fee](https://unity.com/runtime-fee)'.

Almost 20 acquisitions of companies in 10 years. Most of them, in my opinion, were unnecessary or unjustifiable other than to satisfy shareholders' desire for growth.

For me, the **worst thing** that has happened in these 10 years is the chaos generated by the '**Scriptable Render Pipeline**', an interesting idea carried out in the worst possible way:

* Incompatible shader and rendering code between the three existing SRPs.
* Failure to upgrade shaders with the Built-In renderer to another SRP.
* Lack of documentation.

Fortunately Unity is already working on ['Block Shaders'](https://forum.unity.com/threads/block-shaders-surface-shaders-for-srps-and-more-public-demo-now-available.1350497/), something similar to the old Surface Shaders. It has only taken 5 years of complaining.

![Gigaya](/Dawn-Of-The-Cards/images/unity_is_a_harsh_mistress/gigaya.jpg "Gigaya")

The other unforgivable mistake is the cancellation of ['Gigaya'](https://unity.com/demos/gigaya). Unity needs to develop games to offer better solutions and better pipelines to its customers, something Epic has been doing for years with Unreal. 'Gigaya' was going to be the first full game (not tech demo or scripted) of Unity, but someone decided to cancel it and fire the whole team.

And now we have to add the retroactive change, without warning, hiding it and possibly illegal of its TOS. This is something that I think is **much more serious** than the 'Unity Runtime Fee' and that finishes sinking the confidence of the companies with Unity.

> # Today I **cannot recommend Unity** as it has proven that it cannot be trusted.

I really doubt that Unity will still be around in 5 years as it is today if it continues on this course with John Riccitiello.

**Personally, I will continue to use Unity** as a large majority of my current income comes from its [Asset Store](https://assetstore.unity.com/publishers/62716), something in which it far surpasses its competition. The game I am developing is not affected by the 'Unity Runtime Fee' as it will not be F2P.

I just hope Unity comes to its senses, stops buying companies to fatten its stock market value (which is not happening) and **John Riccitiello resigns**.