---
layout: post
title: "Metadata Design"
description: "because you never stop learning."
date: 2019-11-05
---

Even though I've wrapped up the master's program and received my MLS (**thank** the maker), I'm still working through some courses for professional development. Many of the courses that I've taken are available from Library Juice Academy. Just an FYI, I'm not popular or savvy enough to be asked to do an #ad, so this is not an ad...I just really enjoy taking courses from LJA. *Anywho*...I've recently wrapped up a course, [Metadata Design](https://www.libraryjuiceacademy.com/105-metadata-design.php) and it. was. challenging. but *awesome*. I learned so much and feel more prepared to deal with metadata. Here's a brief description of the course:
> Students will learn the tools of metadata design, beginning with the data model that abstracts the meaning and value of the collection, the registry, which formalizes the data model into workable metadata elements, to standardizing the values that populate metadata through ontology and vocabulary development. Students are also introduced to metadata expression, through the collaborative design of an XML schema and through use of XML and RDF to document metadata instances from the schema.


For a final project, we were to create a data model, XML schema, and an XML record for a fictional collection of bird photographs. We examined an aspect of this collection - bird behavior. Below are my XML schema and record submissions.

XML Schema 

```xml
<?xml version="1.0" encoding="UTF-8"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema"
targetNamespace="http://lhs.org/grossvelt/bird.xsd"
xmlns="http://lhs.org/grossvelt/bird.xsd" elementFormDefault="unqualified">
<xs:element name="birdRecord" />
	<xs:element name="birdNote" type="xs:string" />
	<xs:complexType name="birdType">
		<xs:sequence>
			<xs:element name="popularName" type="xs:string"  maxOccurs="unbounded" /> 
			<xs:element name="scientificName" type="xs:string" />
			<xs:element name="number" type="xs:positiveInteger" />
		</xs:sequence>
	</xs:complexType>
	<xs:element name="behavior">
	<xs:simpleType>
		<xs:restriction base="xs:string">
			<xs:enumeration value="Feeding" />
			<xs:enumeration value="Drinking" />
			<xs:enumeration value="Foraging" />
			<xs:enumeration value="Breeding" />
			<xs:enumeration value="Flying" />
			<xs:enumeration value="Singing" />
		</xs:restriction>
	</xs:simpleType>
	</xs:element>
	<xs:group name="birdRecordGroup">
		<xs:sequence>
			<xs:element ref="birdType" maxOccurs="unbounded" />
			<xs:element ref="behavior" minOccurs="0"  maxOccurs="unbounded" /> 
			<xs:element ref="birdNote" minOccurs="0" />
		</xs:sequence>
	</xs:group>
</xs:schema>
```


XML record

```xml
<!-- Bird info.
Scientific name: Bubulcus ibis
Popular name: Cattle egret
Number: 5
Behavior: Breeding
Bird Note: Flock taking flight in response to a dog approaching the tree.
 -->

<?xml version="1.0" encoding="UTF-8"?>
<birdRecord>
	<birdType>
		<popularName>Cattle egret</popularName>
		<scientificName>Bubulcus ibis</scientificName>
		<number>5</number>
	</birdType>
	<behavior>Breeding</behavior>
	<birdNote>Flock taking flight in response to a dog approaching the tree.</birdNote>
</birdRecord>
```
