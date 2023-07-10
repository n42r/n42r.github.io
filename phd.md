---
layout: plain
---
# PhD Project Overview

How can we facilitate the exchange of datasets and other data assets across heterogeneous technical and social environments? This is a classical problem that is more relevant today than ever before, relevant both on a global scale (ex., the exchange of COVID-19 data) and the scale of organizations (horizontal and vertical integration). However, we need to distinguish between two notions of data sharing and exchange: one refers to the integration, federation, and transformation of data at the schema level, and the other, our focus here, refers to the description, publication, discovery, and re-use of data \emph{as an asset} (similar to how a book is managed in a library).

The state-of-the art of the data sharing and exchange problem is polarized. On one end we have emerging *'platforms'* such as the International Data Spaces and Gaia-X, which-if history repeats itself-can susceptible to become walled-gardens that do not interoperate with each other, leading to lock-ins and stifling innovation. On the other end we have *recommendations* such as FAIR guidelines, or architectural abstractions such as *data lake* and *data catalog* that are guidelines or abstractions intended to orchestrate disparate vendors to develop interoperable technologies; taking us in the right direction but not too far. This is due to them being too low-detail/high-level on one side and normative/prescriptive on the other. This work attempts to fill a gap by making a proposal that (1) is constructive (rather than prescriptive) and (2) expands on the level of detail of the existing guidelines.


We propose the *Basin Network model* (BNet model), a distributed data architecture which revolves around two novel abstractions: the *Offering* (message exchange format) and the *Basin* (node). An *Offering* identifies, represents, and describes a data asset but does not include it (i.e., it contains metadata, similar to a record in a data catalog). The Basin is a distributed publish/subscribe node for authoring, managing, and publishing Offerings and exchanging them with other Basins, resulting in a Basin *Network* (akin to a network of data lakes). See Figure below for a conceptual overview.

We demonstrate the applicability of the proposal by applying it to use-cases in three domains: a computer-aided manufacturing project involving eight organizations of varying specializations, sizes, and geographical locations, as well as an IoT project in smart agriculture, and one in crowd data management.\newline


<h1>
  <img src="assets/img/bnet-er.drawio.svg" class="img-fluid" alt="" />
</h1>