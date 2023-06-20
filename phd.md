---
layout: plain
---
# The Basin Network: A Model for Data Sharing and Exchange

How can we facilitate the exchange of datasets and other data assets across heterogeneous technical and social environments? This is a classical problem that is more relevant today than ever before, relevant both on a global scale (ex., the exchange of COVID-19 data) as well as the scale of organizations (horizontal and vertical integration). However, we need to distinguish between two notions of data sharing and exchange: one based on the integration, federation, virtualization, and transformation of data at the schema level, and the other, which is our focus here, based on the description, publication, discovery, compilation, and re-use of data \emph{as an asset} (akin to how a book is managed in a library, for example).

The state-of-the art of the data sharing and exchange problem is polarized. On one end we have emerging *'platforms'* such as the International Data Spaces and Gaia-X, which-if history repeats itself-can susceptible to become walled-gardens that do not interoperate with each other, leading to lock-ins and stifling innovation. On the other end we have *recommendations* such as FAIR guidelines, or architectural abstractions such as *data lake* and *data catalog* that are standards, guidelines, or abstractions intended to orchestrate disparate vendors to develop interoperable technologies; taking us in the right direction but not too far. This is due to them being too high-level, more normative/prescriptive than constructive, and uncoordinated. This work attempts to fill a gap by making a proposal that (1) meets the aforementioned normative/prescriptive recommendations and (2) builds on and expands the existing constructive recommendations, resulting in a novel, *'medium-level'* recommendation in the form of an architectural model.


We propose the *Basin Network model* (BNet model), a distributed system model which revolves around two novel abstractions: the *Offering* (message exchange format) and the *Basin* (node). We adopt an *indirection* approach: a data asset is managed and exchanged via a *surrogate* (intermediate representation) which identifies, represents, describes, and effectively *'stands in'* for it. The Offering is a model for such surrogates; built on the *URI-Resource* framework for hypermedia authoring but avoids some of its longstanding confusions over the nature of the URI-Resource. The Basin is a distributed publish/subscribe-based model for authoring, managing, and publishing Offerings and exchanging them with other Basins, resulting in a Basin *Network* (akin to a network of data lakes). See Figure below for a conceptual overview.

We demonstrate the applicability of the proposal by applying it to use-cases in three domains: a multi-year computer-aided manufacturing project we were involved in that included eight organizations of varying specializations, sizes, and geographical locations, as well as an IoT project in smart agriculture, and one in crowd data management.

<h1>
  <img src="assets/img/bnet-er.drawio.svg" class="img-fluid" alt="" />
</h1>