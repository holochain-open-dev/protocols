# Protocols for Dna Properties

## Problem

Dna properties are a really useful tool to configure Dnas. However, since all zomes in that Dna need to share the same properties object, the slightest difference in spelling would make two zomes not really compatible with each other in the same Dna.

Example:

- In zome A we expect this property: `number_of_agents_allowed: u64`.
- In zome A we expect this property: `number_agents_allowed: u64`.
- The two zomes agree on what the property means.
- In the Dna properties we need to duplicate the property to cover both zomes.
