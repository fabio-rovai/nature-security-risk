# A systems framework for nature-related security risk

This is the conceptual spine of the evidence base. It takes the systems approach the UK Nature Security Assessment (2026) asks for, complexity, tipping points, feedback loops, risk cascades and compounding shocks, and makes each construct a first-class, machine-readable object rather than a figure in a report.

## The cascade spine

Every entry in [`../data/cascades.csv`](../data/cascades.csv) is an instance of one structure:

```
Driver  ->  Ecosystem-service loss  ->  Transmission channel  ->  Security outcome
(IPBES drivers)   (IPBES NCP decline)      (the security layer)     (human / geopolitical)
```

The upstream half (driver -> service loss) is deliberately borrowed from the **IPBES conceptual framework**: we do not re-model nature. The downstream half (channel -> outcome) is the layer the field is missing, the *threat -> consequence -> national-interest* grammar that indicator systems such as BII, Aqueduct, ND-GAIN, TNFD and SEEA never carry, because they were built for conservation, water, adaptation, finance and accounting, not security.

## The four systems constructs, operationalised

The NSA names four systems properties. Each is a modelled object in [`../ontology/nsro.ttl`](../ontology/nsro.ttl):

1. **Complexity.** A cascade is a typed graph, not a line. A single driver can open several channels (Lake Chad: fisheries *and* grazing *and* freshwater), and a single outcome can have several drivers (Sahel conflict: degradation *and* governance *and* water).
2. **Tipping points** (`nsro:TippingPoint`). A threshold beyond which change becomes self-sustaining (Amazon dieback, AMOC). These carry the early-warning statistics in [`../indicators/methods.md`](../indicators/methods.md).
3. **Feedback loops** (`nsro:FeedbackLoop`, `nsro:reinforces`). The reinforcing edge where an outcome degrades adaptive capacity and amplifies the driver, exactly the Lake Chad finding that conflict erodes resilience as much as ecosystem stress drives conflict.
4. **Compounding shocks** (`nsro:CompoundShock`). Two or more concurrent drivers or channels that interact and amplify (2010 multi-breadbasket wheat shock plus export bans; drought plus conflict-driven access denial in the 2011 Somalia famine).

## Why the two contested cases are kept, not dropped

The Syria drought-to-war chain (NSR-03) and the food-price-to-Arab-Spring chain (NSR-02) are the field's most cited and most disputed cascades. We keep both, flag them `contested = Yes`, and cite **both** the claim (Kelley et al. 2015) and its rebuttal (Selby et al. 2017). This is the discipline the securitisation critique (Tebboth et al. 2026) demands: nature loss is a **threat multiplier interacting with governance, poverty and markets**, almost never a sole cause. The confidence rating on each cascade encodes exactly how much weight the chain can bear.

## From framework to the three government functions

- **Assess** reads the framework left-to-right: given a country's ecosystem-service exposure, which channels are open and which outcomes become plausible.
- **Monitor** watches the leading edges: driver-side early-warning signals for tipping points, and channel-side leading indicators (food-price volatility, water stress, displacement).
- **Mitigate** reads the framework as an intervention map: every cascade carries the point at which the chain is cheapest to break, cross-referenced to a policy lever (National Risk Register, IPBES response options, Kunming-Montreal targets).
