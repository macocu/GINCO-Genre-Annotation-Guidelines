---
layout: entry
title: Guidelines for Manual Checking of the Web Corpora
---

The purpose of task is to detect low quality domains which can be removed before we continue with additional processing of the corpora. We search for *bad* domains which contain so few full sentences, written in the target language, that is it better to remove the whole domain than try to filter out just problematic parts. Such examples are websites that are entirely machine translated, entirely in foreign language or contain no full sentences (just lists). If the domain includes some problematic texts, but also some okay content, such domain should be marked as *low-quality* (*lq*) instead of *bad*, as we want to keep as much text of good quality as possible.

For each domain, there is a link to the live site and a link to random triples of sentences in context to see the actual content of the sites in Sketch Engine. We thoroughly check just the top 350 domains. Other, smaller domains (up to 1200 additional domains) are checked only in the case when their name is suspicious.

## Table of contents
* [What do we check?](#what-do-we-check)
* [Steps](#steps)
* [Solved dilemmas](#solved-dilemmas)
* [Topics](#topics)


## What do we check?
* (obvious) machine translation (more details on how to recognize it [here](_pages/machine_translation.md)).
* generated text ([examples](_pages/generated_text_examples.md))
* foreign language
* lists (no full sentences) ([examples](_pages/non-textual_examples.md))
* HTML Source Code/Markdown ([examples](_pages/markdown_examples.md))

## Steps

1. Read the examples from the domain:
	* The top 20 domains should be thoroughly checked:
		*skim through all of the concordances in the Sketch Engine (column C), looking for machine translation, generated text, foreign language, lists (no full sentences), HTML source code or markdown (unusual elements in the running text)

	* For the remaining first 350 domains skimming through the first 15 concordances is enough, checking for the same as above

	* After checking the first 350 domains, just go through the URLs (column B) of the next 1200 domains (so that 1500 domains are checked) and check only those that seem highly suspicious, e. g.:
		* they have "porn" or other unusual words in the name
		* they do not use the national domain - especially if they use the `.eu` domain or a domain of a country with a closely related language
		* the domain name begins with the language code (it is very likely that the domain is machine translated)
		* the URL link is not clickable

2. Mark the domain as *ok*, *check*, *lq* (low quality), *bad* or *issue* (column D):
	* if there are **no issues** -> *ok*
	* if there are **some issues**, but the majority of page is okay -> *lq* + add a note which issue is present (column E)
	* if the text could be **machine translation**, but you are not sure -> *lq* + note "possible machine translation" (column E)
	* if there are **mostly issues**, i.e. most of the concordances contain issues -> *bad* + add a note what is the issue (column E)
	* if you encountered a phenomena not described in the guidelines and don't know what to do -> *issue* + add a note describing the phenomena, and open [an issue](https://github.com/macocu/Manual-Checking-Web-Corpora-Guidelines/issues) on the GitHub
	* *check*:
		* if most of the concordances are **repeated text** (such as shipping conditions), text regarding **cookies** ([examples](_pages/cookies_examples.md)) -> *check* + add a note *"duplicated"* (column E)
		* if there are **encoding issues** present in concordances -> *check* + add a note *"encoding"* (column E)
		* if there are issues with **HTML source code/markdown** --> *check* + add a note *"markdown"* (column E)

3. (Optional) Add information on topic (if there are multiple topics or you are not sure, leave empty, do not spend much time deciding on the topic):
	* choose from the [proposed topic labels](#topics), if you feel that there are additional broad topics present in multiple domains, you can use additional topics.

4. (Optional) Add information on genre if all concordances are in the same genre. Choose from the following labels (if none is applicable, leave empty):
	* news portal
	* legal/regulation - legal texts
	* recipe
	* forum
	* promotion of services - all texts promote services of companies
	* e-shop (includes platforms that provide accomodation (e.g. Booking/AirBnB-like content))
	* research article (abstracts, theses, research articles)
	* opinion (blogs, petitions - author's opinion is very obvious, visible)
	* literature (prose, poetry, drama)
	* small ads (advertisement websites where users post their ads)

5. (Optional) If the language on the page seems **unedited** (many typos) or **non-standard** (very informal language, such as in forums, includes historic language), mark that by *Y* in column I

Mark only sites that were checked - content with an empty value in column D is considered unchecked and will be kept in the corpus.

## Solved dilemmas

* dictionary entries -> *lq* + add a note *"dictionary"* in column E, if there is more foreign language than Slovene -> *bad*
* older varieties of language (e.g. in old literature) -> *okay*, mark non-standardness of text by *Y* in column I


## Topics

* academic (research articles, theses)
* animals
* astrology
* beauty (including make-up, fashion, clothes, shoes, fabrics etc.)
* business (includes economy and finance)
* cars
* community (municipality sites, town sites)
* construction & real estate (includes arhitecture and urbanism)
* culture (books, theatre, opera)
* engineering (machines, machine parts, electroengineering etc.)
* environment
* entertainment (movies, music, events …)
* family (includes all topics/products connected to children)
* food & drinks (includes products involved in food preparation, e.g. dishes)
* gambling & casinos
* history (includes biographies)
* hobbies (shooting, gaming, railway enthusiasts etc. - sport hobbies are included in "sport")
* home & garden
* law
* love & sex
* politics
* public safety (fire-fighting, police, mountain rescue etc.)
* religion
* science (chemistry, medicine etc. - but not written in a form of a research article, thesis)
* services (includes job offers)
* sport (includes sport hobbies, e.g. hiking, yacting, cycling)
* technology (IT, programming, computers, phones, cameras, etc.)
* traffic (includes transport)
* travel
* well-being (physical, mental health; includes diets, fitness, wellness)