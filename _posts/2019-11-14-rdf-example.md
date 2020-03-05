---
layout: post
title: "RDF, RDFa and Structured Data Vocabularies"
date: 2019-11-14
---

As part of Library Juice Academy's Certificate in XML and RDF-Based Systems, I am taking the course RDF, RDFa and Structured Data Vocabularies. In the second exercise, we are to use a bare HTML template and add RDFa 1.1 Lite to the content of the HTML template. If you enter the code below into [RDFa Play](http://rdfa.info/play/), you can see a visualization of the how the RDF content is arranged and the Raw Data. It's pretty interesting how this works: on the front end, all that is seen is the paragraph. Very nondescript, very plain. But the RDFa 1.1 Lite attributes sprinkled throughout the paragraph creates descriptive metadata so an RDFa-aware processor or search engine will be able to extract this information and for example, link my data to other items on the web.


```HTML
<!DOCTYPE html SYSTEM "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <title>Assignment 2</title>
    </head>
    <body>
        <div vocab="http://schema.org/" typeof="CreativeWork" resource="http://www.worldcat.org/oclc/1020463016" prefix="dcterms:http://purl.org/dc/terms/">
         <!-- borrowed from https://en.wikipedia.org/wiki/Kindred_(novel) -->
             <span property="dcterms:title">Kindred</span> is a <span property="genre">novel</span> by American writer <span property="creator">Octavia E. Butler</span> that incorporates <span property="dcterms:subject">time travel</span> and is modeled on slave narratives. First published in <span property="dcterms:date">1979</span>, it is still widely popular. It has been frequently chosen as a text for community-wide reading programs and book organizations, as well as being a common choice for high school and college courses. The book is the <span property="about">second-person account of a young African-American woman writer, <span property="character">Dana</span>, who finds herself being shunted in time between her <span property="dcterms:spatial">Los Angeles, California</span> home in <span property="dcterms:temporal">1976</span> and a <span property="dcterms:temporal">pre-Civil War</span> <span property="dcterms:spatial">Maryland</span> plantation.</span> There she meets her ancestors: a proud black freewoman and a white planter who has forced her into slavery and concubinage. As Dana's stays in the past become longer, the young woman becomes intimately entangled with the plantation community. She makes hard choices to survive slavery and to ensure her return to her own time. Kindred explores the dynamics and dilemmas of antebellum slavery from the sensibility of a late 20th-century black woman, who is aware of its legacy in contemporary American society. Through the two interracial couples who form the emotional core of the story, the novel also explores the intersection of <span property="dcterms:subject">power</span>, <span property="dcterms:subject">gender</span>, and <span property="dcterms:subject">race issues</span>, and speculates on the prospects of future egalitarianism.
        </div>
    </body>
</html>
```
