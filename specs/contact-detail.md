---
layout: class
title: Contact detail | Popolo
id: contact-detail
---

<ul class="breadcrumb">
  <li><a href="/specs/">Data Specification</a></li>
  <li><a href="/specs/#classes-and-properties">Classes and properties</a></li>
  <li class="active">Contact detail</li>
</ul>

<h1 id="use-cases-and-requirements">1. Use cases &amp; requirements</h1>

It is impossible to predict the means by which people will be contacted: from mail and telephones to email and <abbr title="Voice over Internet Protocol">VoIP</abbr>. Some contact details are related to physical locations, like an office's postal address and fax number, while others are not, like a person's mobile number and email address. To support the widest variety of mediums in the widest range of contexts, the Contact detail class should allow user-defined contact details.

<div class="well well-sm well-example">
  <p>A civil society organization has the phone number of a legislator; however, it doesn't know whether it is the capitol office number, the constituency office number or a mobile number. A suitable specification should be able to handle data at varying levels of precision.</p>
</div>

The Contact detail class should have properties for:

1. label

    >e.g. "Hill address" or "Mobile number".

1. type of medium

    >e.g. "address" or "cell".

1. value

    >e.g. a postal address, mobile number, email address, contact form, etc.

1. note

    >e.g. for grouping contact details by physical location.

1. the date from which the contact detail is valid

    >A member of parliament is changing address as of next month.

1. the date from which the contact detail is no longer valid

    >Three years ago, an MP's office shared an address with a business whose owner the MP presently claims not to know.

<h1 id="standard-reuse">2. Standard reuse</h1>

The [survey of existing specifications](/appendices/survey.html) found that [RFC 6350 (vCard 4.0)](http://tools.ietf.org/html/rfc6350), with its RDF mappings, is the only vocabulary to meet all [requirements](#use-cases-and-requirements). Few specification allow for the ad hoc definition of contact details. Ultimately, only the data model – consisting of RDF, RDF Schema, and <abbr title="Simple Knowledge Organization System">SKOS</abbr> terms – was reused.

<h1 id="classes-and-properties">3. Classes and properties</h1>

<table>
  <thead>
    <tr>
      <th width="130">Term</th>
      <th>Mapping</th>
      <th>Definition</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Contact detail</strong></td>
      <td>No <code>rdf:type</code></td>
      <td>A means of contacting an entity</td>
    </tr>
    <tr id="rdfs:label">
      <td>label</td>
      <td><code><a href="http://www.w3.org/TR/rdf-schema/#ch_label" title="http://www.w3.org/2000/01/rdf-schema#label">rdfs:label</a></code></td>
      <td>A human-readable label for the contact detail</td>
    </tr>
    <tr id="rdf:type">
      <td>type of medium</td>
      <td><code><a href="http://www.w3.org/TR/rdf-schema/#ch_type" title="http://www.w3.org/1999/02/22-rdf-syntax-ns#type">rdf:type</a></code><a href="#note1"><sup>1</sup></a></td>
      <td>A type of medium, e.g. "fax" or "email"</td>
    </tr>
    <tr id="rdf:value">
      <td>value</td>
      <td><code><a href="http://www.w3.org/TR/rdf-schema/#ch_value" title="http://www.w3.org/1999/02/22-rdf-syntax-ns#value">rdf:value</a></code></td>
      <td>A value, e.g. a phone number or email address</td>
    </tr>
    <tr id="skos:note">
      <td>note</td>
      <td><code><a href="http://www.w3.org/TR/skos-reference/#notes" title="http://www.w3.org/2004/02/skos/core#note">skos:note</a></code></td>
      <td>A note, e.g. for grouping contact details by physical location</td>
    </tr>
    <tr id="schema:validFrom">
      <td>valid from</td>
      <td><code><a href="http://schema.org/validFrom" title="http://schema.org/validFrom">schema:validFrom</a></code></td>
      <td>The date from which the contact detail is valid</td>
    </tr>
    <tr id="schema:validUntil">
      <td>valid until</td>
      <td><code><a href="http://schema.org/validUntil" title="http://schema.org/validUntil">schema:validUntil</a></code></td>
      <td>The date from which the contact detail is no longer valid</td>
    </tr>
  </tbody>
</table>

<p class="note" id="note1">1. The <a href="http://www.w3.org/TR/vcard-rdf/#Code_Sets">vCard Ontology</a> uses <code>rdf:type</code> to indicate the type of address or telephone number.</p>

<h1 id="serialization">4. Serialization</h1>

* Telephone number values <em class="rfc2119">should</em> be in [RFC 3966](http://tools.ietf.org/html/rfc3966) format, without the `tel:` prefix.

<ul class="nav nav-tabs no-js">
  <li><a href="#contact-detail-schema">JSON Schema</a></li>
  <li><a href="#contact-detail-context">JSON-LD Context</a></li>
  <li class="active"><a href="#contact-detail-json">JSON</a></li>
  <li><a href="#contact-detail-rdf">RDF</a></li>
</ul>

<div class="tab-content no-js">
  <div class="tab-pane" id="contact-detail-schema" data-url="/schemas/contact_detail.json"></div>
  <div class="tab-pane" id="contact-detail-context" data-url="/contexts/contact_detail.jsonld"></div>
  <div class="tab-pane active" id="contact-detail-json" data-url="/examples/contact_detail.json"></div>
  <div class="tab-pane" id="contact-detail-rdf" data-url="/examples/contact_detail.ttl"></div>
</div>

<h1 id="code-lists">5. Code lists</h1>

## Type of medium

Implementations <em class="rfc2119">may</em> use values from outside the following lists.

<table id="medium-types">
  <caption>Types of medium code list</caption>
  <thead>
    <tr>
      <th>Value</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>address</code></td>
      <td>A postal address</td>
    </tr>
    <tr>
      <td><code>email</code></td>
      <td>An email address</td>
    </tr>
    <tr>
      <td><code>url</code></td>
      <td>A URL to a contact form, etc.</td>
    </tr>
  </tbody>
</table>

The following is a copy of [RFC 6350 (vCard 4.0)](http://tools.ietf.org/html/rfc6350#section-6.4.1)'s code list.

<table id="telephone-types">
  <caption>Types of medium (telephone types) code list</caption>
  <thead>
    <tr>
      <th>Value</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>text</code></td>
      <td>A telephone number primarily supporting text messages (SMS)</td>
    </tr>
    <tr>
      <td><code>voice</code></td>
      <td>A voice telephone number</td>
    </tr>
    <tr>
      <td><code>fax</code></td>
      <td>A facsimile telephone number</td>
    </tr>
    <tr>
      <td><code>cell</code></td>
      <td>A mobile telephone number</td>
    </tr>
    <tr>
      <td><code>video</code></td>
      <td>A video conferencing telephone number</td>
    </tr>
    <tr>
      <td><code>pager</code></td>
      <td>A paging device telephone number</td>
    </tr>
    <tr>
      <td><code>textphone</code></td>
      <td>A telecommunication device for people with hearing or speech difficulties</td>
    </tr>
  </tbody>
</table>
