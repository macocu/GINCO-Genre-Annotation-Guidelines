---
layout: entry
title: Guidelines for Manual Checking of the Web Corpora
---

The purpose of this task is to detect low quality domains which can be removed before we continue with additional processing of the corpora. We search for *bad* domains which contain so few good-quality sentences of the target language that is it better to remove the whole domain than try to filter out just problematic parts. Such examples are websites that are entirely machine translated or entirely in foreign language. If the domain includes some problematic texts, but also some good-quality content, such domain should be marked as *low-quality* (*lq*) instead of *bad*, as we want to keep as much text of good quality as possible. For more details on when to mark the domain *bad*, see the section [Additional Details](#additional-details).

For each domain, there is a link to the live site and a link to random triples of sentences (known as concordances) in context to see the actual content of the sites in Sketch Engine. We thoroughly check just the top 350 domains. Other, smaller domains (up to 1200 additional domains) are checked only in the case when their name is suspicious.

## Table of contents
* [What do we check?](#what-do-we-check)
* [Steps](#steps)
* [Solved dilemmas](#solved-dilemmas)
* [Topics](#topics)
* [Additional Details](#additional-details)


## What do we check?
* (obvious) machine translation (more details on how to recognize it [here](_pages/machine_translation.md)).
* generated text ([examples](_pages/generated_text_examples.md))
* foreign language
* lists (no full sentences) ([examples](_pages/non-textual_examples.md))

## Steps

1. Read the examples from the domain:
	* The top 20 domains should be thoroughly checked:
		* skim through all of the concordances in the Sketch Engine (link in the column C), looking for machine translation, generated text, foreign language, lists (no full sentences), HTML source code or markdown (unusual elements in the running text - [examples](_pages/markdown_examples.md))

	* For the remaining first 350 domains skimming through the first 15 concordances is enough, checking for the same as above

	* After checking the first 350 domains, just go through the URLs (column B) of the next 1200 domains (so that 1500 domains are checked) and check only those that seem highly suspicious, e. g.:
		* they have "porn" or other unusual words in the name
		* they do not use the national domain, e.g. ".si" - especially if they use the `.eu` domain or a domain of a country with a closely related language
		* the domain name begins with the language code, e.g. "sl.toolbox-site.com" (it is very likely that the domain is machine translated)
		* the URL link is not clickable

2. Mark the domain as *ok*, *check*, *lq* (low quality), *bad* or *issue* (column D):
	* if there are **no issues** -> *ok*
	* if there are **some issues**, but the majority of page is okay -> *lq* + add a note which issue is present (column E)
	* if the text could be **machine translation**, but it is not very obvious (it could be a very good machine translation) -> *lq* + note "possible machine translation" (column E)
	* if there are **mostly issues**, i.e. most of the concordances contain issues (foreign language, machine translation, non-textual etc.), there is so little good-quality text that the whole domain should be discarded from the corpus -> *bad* + add a note what is the issue (column E)
	* if you encountered a phenomena not described in the guidelines and don't know what to do -> *issue* + add a note describing the phenomena, and open [an issue](https://github.com/macocu/Manual-Checking-Web-Corpora-Guidelines/issues) on the GitHub
	* *check*:
		* if most of the concordances are **repeated text** (such as shipping conditions), text regarding **cookies** ([examples](_pages/cookies_examples.md)) -> *check* + add a note *"duplicated"* (column E)
		* if there are **encoding issues** (issues with special characters, such as š, č, ć) present in concordances -> *check* + add a note *"encoding"* (column E)
		* if there are issues with **HTML source code/markdown** --> *check* + add a note *"markdown"* (column E)

3. (Optional) Add information on topic (if there are multiple topics or you are not sure, leave empty, do not spend much time deciding on the topic):
	* choose from the [proposed topic labels](#topics), you can extend the list of topics with other common broad topics if needed.

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

5. (Optional) If the language on the page seems **unedited** (many typos) or **non-standard** (very informal language, such as in forums, or historic language), mark that by *Y* in column I

Mark only sites that were checked - content with an empty value in column D is considered unchecked and will be kept in the corpus.

## Solved dilemmas

* dictionary entries -> *ok*, if most sentences are in a foreign language -> *bad*
* older varieties of language (e.g. in old literature) -> *ok*, mark non-standardness of text by *Y* in column I
* search engine domains --> *ok*
* domains that include corpora --> *ok*
* text, concatenated with - (no spaces between words: "Lastnik-stanovanja-je-po-smrti-najemnika-dolžan") --> If the issue is present in all/almost all examples, mark as *bad*, otherwise, mark as *lq* and add a note about it in column E.

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
* public safety (fire-fighting, police, army, mountain rescue etc.)
* religion
* science (chemistry, medicine etc. - but if it is written in a form of a research article, thesis, the topic is academic)
* services (includes job offers)
* sport (includes sport hobbies, e.g. hiking, yacting, cycling)
* technology (IT, programming, computers, phones, cameras, etc.)
* traffic (includes transport)
* travel
* well-being (physical, mental health; includes diets, fitness, wellness, classic and alternative medicine)

## Additional Details

### Issues and how we address them with processing methods
* machine translation – no automatic method for filtering -> if you have reason to believe that most of the domain is machine-translated, mark the domain as *bad*
* generated text – no automatic method for filtering -> if 75% of page or more is generated text, mark as *bad*
* foreign language – paragraphs in another language will be detected with automatic language identifier. However, the identifier might not be able to differentiate between closely related languages, e.g. between Serbian and Croatian -> mark the page as *bad* if everything is in another language; mark as *bad* if most of the page is in related language
* non-textual (lists, no full sentences) – word phrases in the target language might still be useful for us, we don’t necessarily want to discard such pages -> prefer marking it as *low quality*

Otherwise, whenever the issues are present, but do not meet the criteria for *bad*, mark as *low quality*. If you are not sure whether the domain is "bad enough”, mark it as *low quality*.

**Additional issues**:
* encoding issues, HTML markup – we will implement rules to correct them -> mark as *check* + note “encoding”/”markup” whenever they are present in the domain

### How much to check?
* if the domain is entirely *bad* that will be quickly visible
* the lower the domain on the list, less needs to be checked – from 20th domain onward, skimming through the first 15 concordances is enough. No need to read the whole concordance, just skim through the beginning of it, just enough to be able to say whether the text is machine translation/generated text/closely related language or not.
