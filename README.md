# Family Relationships Ontology

This small OWL ontology models people and family relationships in RDF/Turtle. It demonstrates how inverse properties and class restrictions let an OWL reasoner infer relationships and classify individuals from stated facts.

## What it models

| Term | Definition |
| --- | --- |
| `Person` | The class of people in the ontology. |
| `HappyPerson` | A subclass of `Person`. |
| `hasChild` and `childOf` | Inverse object properties. The domain and range of `hasChild` are both `Person`. |
| `Parent` | A person with at least one `hasChild` relationship to a `Person`. |
| `HappyParent` | A `Parent` whose `hasChild` relationships point only to instances of `HappyPerson`. |

## Open and explore

1. Install the Protégé desktop ontology editor.
2. Download [`protege.ttl`](protege.ttl) from this repository and open it in Protégé with **File → Open**.
3. In **Object properties**, select `hasChild` and inspect its inverse, domain, and range. In **Classes**, select `Parent` and `HappyParent` to inspect their equivalent class definitions.
4. Select an available OWL reasoner in the **Reasoner** menu and start it to inspect inferred classifications.

## Example

The ontology asserts that Carol has Alice and Bob as children. The inverse property axiom entails that Alice and Bob are each `childOf` Carol. Carol also satisfies the definition of `Parent`.

OWL uses an open-world assumption. Two listed children alone do not establish that Carol has no others. The ontology includes a separate restriction that limits Carol’s children to Alice and Bob, both asserted as instances of `HappyPerson`.
