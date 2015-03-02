---
layout: default
title: Terms
id: data
---
{% include navigation.html %}

<ul class="breadcrumb">
  <li><a href="/specs/">Data Specification</a></li>
  <li>Appendices</li>
  <li class="active">Inventory of terms from survey</li>
</ul>

# Namespaces

&namespaces

# Classes

* People and organizations
  * [Person](#Person)
  * [Organization](#Organization)
  * [Membership](#Membership)
  * [Post](#Post)
  * [Address](#Address)
* Motions and voting
  * [Motion](#Motion)
  * [Vote event](#VoteEvent)
  * [Count](#Count)
  * [Vote](#Vote)
* Other classes
  * [Area](#Area)
  * [Event](#Event)
  * [Speech](#Speech)

The [PML Schema](http://www.liparm.ac.uk/?page_id=103) reuses the properties `sources`, `externalLinks`, `startDate` and `endDate` across classes.

<h2 id="Person">Person</h2>

* vCard's terms are from the [RDF encoding](http://www.w3.org/TR/vcard-rdf/) of vCard 4.0, except for `DEATHDATE` which is from [RFC 6474](http://tools.ietf.org/html/rfc6474).

&person

<h2 id="Organization">Organization</h2>

* Schema.org adds a new property for each identifier scheme, e.g. `duns`, `globalLocationNumber`, `taxID` and `vatID`, and each classification scheme, e.g. `isicV4` and `naics`.
* In PML Schema, organizational hierarchies can have a maximum depth of five.

&organization

<h2 id="Membership">Membership</h2>

* In PML Schema, memberships are embedded on `person` objects.

&membership

<h2 id="Post">Post</h2>

* PML Schema has the properties `startDate` and `endDate` for the dates of creation and elimination.

&post

<h2 id="Address">Address</h2>

* To disambiguate between different telephone types, Schema.org adds [faxNumber](http://schema.org/PostalAddress), LDAP adds [mobile](http://tools.ietf.org/html/rfc4524#section-2.18), [pager](http://tools.ietf.org/html/rfc4524#section-2.20) and [facsimileTelephoneNumber](http://tools.ietf.org/html/rfc4519#section-2.10) and NIEM adds `ContactFaxNumber`, `ContactMobileTelephoneNumber` and `ContactPagerNumber`.
* LDAP adds properties like [homePostalAddress](http://tools.ietf.org/html/rfc4524#section-2.13) to disambiguate between different address types.

&address

<h2 id="Motion">Motion</h2>

* Canada has two ways of expressing motions: from the [votes list page](http://www.parl.gc.ca/housechamberbusiness/Chambervotelist.aspx?Language=E) and from the vote detail page.
* [Czech Republic](http://www.psp.cz/sqw/hp.sqw?k=1300) publishes data on motions declared confusing.
* [Ireland](http://oireachtasdebates.oireachtas.ie/debates%20authoring/debateswebpack.nsf/%28votesasxmlDail%29?openview) doesn't distinguish between motions and vote events.
* [Italy](http://dati.camera.it/ocd/reference_document/) doesn't define a Motion class, but we list the properties shared with the VoteEvent class.
* Norway publishes voting records as [CSV](https://data.stortinget.no/bygger/votering?pr=59583&dt=Table&vo=5092) and [XML](http://data.stortinget.no/eksport).
* [Sweden](http://data.riksdagen.se/Data/Voteringar/) classifies motions as `sakfrågan` or `motivfrågan`. "rm" is an abbreviation of "Riksmöte".
* Switzerland offers an [API](http://ws.parlament.ch/) and [bulk downloads](http://www.parlament.ch/f/wahlen-abstimmungen/abstimmungen-im-parlament/Pages/abstimmung-nr-xml.aspx).
* Canada, [Germany](http://www.bundestag.de/bundestag/plenum/abstimmung/2014), the [US House](http://clerk.house.gov/legislative/legvotes.html) and the [US Senate](http://www.senate.gov/legislative/LIS/roll_call_lists/vote_menu_113_2.htm) have terms for the session's legislature: `parliament`, `Wahlperiode`, `congress` and `congress`, respectively.
* Canada and [Toronto](http://app.toronto.ca/tmmis/getAdminReport.do?function=prepareMemberVoteReport) have terms for meetings: `sitting` and `meeting`, respectively.

&motion

<h2 id="VoteEvent">Vote event</h2>

* Canada has three ways of expressing votes: in the [Hansard](http://www.parl.gc.ca/HouseChamberBusiness/ChamberSittings.aspx?View=H&Language=E), from the [votes list page](http://www.parl.gc.ca/housechamberbusiness/Chambervotelist.aspx?Language=E) and from the vote detail page.
* Czech Republic records repeat votes, along with the person requesting the repeat.
* Toronto publishes reports for each voter.
* Switzerland has the properties `meaningYes` and `meaningNo` for the meaning of voting "Yes" or "No".

&voteevent

<h2 id="Count">Count</h2>

* The [Cornell Legal Information Institute Legislative Metadata Project](http://blog.law.cornell.edu/metasausage/downloads-and-related-information/) has explicit properties for counts: `hasYeaTally`, `hasNayTally` and `hasNoVoteTally`.
* [Brazil](http://www.camara.leg.br/internet/plenario/result/votacao/Layout_ArquivosTXT_presencas_vota%C3%A7%C3%A3o_exportados.pdf) has explicit columns for counts: `SIM`, `NÃO`, `ABSTENÇÃO`, `OBSTRUÇÃO` and `BRANCO`.
* [Bulgaria](http://www.parliament.bg/bg/plenaryst) has explicit properties for counts: `За`, `Против`, `Въздържали` and `се Гласували`.
* Canada has explicit properties for counts on its votes list page: `TotalYeas`, `TotalNays` and `TotalPaired`.
* Czech Republic has explicit properties for counts: `pro`, `proti`, `zdrzel` and `nehlasoval`.
* [Georgia](http://votes.parliament.ge/en/api/v1) has explicit properties for counts: `yes_votes`, `no_votes`, `abstain_votes` and `absent`.
* [Hong Kong](http://www.legco.gov.hk/general/english/open-legco/open-data.html) has explicit properties for counts (`present-count`, `yes-count`, `no-count`, and `abstain-count`) and for groups (`functional-constituency` and `geographical-constituency`).
* Ireland has explicit properties for options: `membersvotedyes`, `membersvotedno` and `membersabsent`.
* Italy has explicit properties for counts: [`favorevoli`](http://dati.camera.it/ocd/reference_document/#favorevoli), [`contrari`](http://dati.camera.it/ocd/reference_document/#contrari), [`astenuti`](http://dati.camera.it/ocd/reference_document/#astenuti), [`votanti`](http://dati.camera.it/ocd/reference_document/#votanti) and [`presenti`](http://dati.camera.it/ocd/reference_document/#presenti).
* Norway has explicit properties for counts: `antall_for`, `antall_ikke_tilstede` and `antall_mot`.
* [Spain](http://www.congreso.es/portal/page/portal/Congreso/Congreso/Actualidad/Votaciones) has explicit properties for counts: `Presentes`, `AFavor`, `EnContra`, `Abstenciones` and `NoVotan`.
* The US House has explicit properties for counts: `yea-total`, `nay-total`, `present-total` and `not-voting-total`.
* The US Senate has explicit properties for counts: `yeas`, `nays`, `present` and `absent`.

&count

<h2 id="Vote">Vote</h2>

* Brazil has both [DBF files](http://www.camara.leg.br/internet/votacao/listavotacao5404.asp) and [fixed-width text files without headers](http://www.camara.leg.br/internet/plenario/result/votacao/downlvnv54.htm) that follow [a schema](http://www.camara.leg.br/internet/plenario/result/votacao/Layout_ArquivosTXT_presencas_vota%C3%A7%C3%A3o_exportados.pdf).
* Canada has explicit properties for options on its vote detail page: `Yea`, `Nay` and `Paired`.
* Germany has explicit properties for options: `ja`, `nein`, `Enthaltung`, `ungültig` and `nichtabgegeben`.
* Ireland has explicit properties for options: `membersvotedyes`, `membersvotedno` and `membersabsent`.
* Norway occasionally has explicit properties for options: `For` and `Mot`.

&vote

<h2 id="Area">Area</h2>

* Schema.org adds a new property for each identifier scheme, e.g. `globalLocationNumber`, and each classification scheme, e.g. `isicV4`.
* FAO adds a new property for each identifier scheme, e.g. `codeDBPediaID`.

&area

<h2 id="Event">Event</h2>

* The [NEPOMUK Calendar Ontology (NCAL)](http://www.semanticdesktop.org/ontologies/2007/04/02/ncal/#sec-introduction) has a detailed discussion of prior work.
* The [Simple Event Model (SEM)](http://www.cs.vu.nl/~guus/papers/Hage11b.pdf) has an accompanying paper.
* [RFC 5545](http://tools.ietf.org/html/rfc5545) specifies the iCalendar data format.

&event

<h2 id="Speech">Speech</h2>

* The Akoma Ntoso terms are from [`speechAtts`](http://examples.akomantoso.org/categorical.html#speechAttsAG), [`show`](http://examples.akomantoso.org/categorical.html#showAG) and [`ANcontainers`](http://examples.akomantoso.org/categorical.html#ANcontainersEG).

&speech
