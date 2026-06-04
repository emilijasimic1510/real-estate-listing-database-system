# Database Design

## Project Topic

The project represents an information system for a real estate agency.

The system is designed to support the process of managing real estate property listings. It stores data about agencies, agents, owners, properties, listings, listing images, clients, inquiries, property categories, and locations.

In a real business environment, property owners provide information about properties they want to sell or rent. An agent working for the agency creates a listing for the property, adds relevant information and images, and publishes it as an offer. Clients can then review available listings and send inquiries related to properties they are interested in.

The main purpose of the system is to provide structured data storage, maintain relationships between properties and listings, and support the tracking of client interest through inquiries.

---

## Selected Subsystem

The selected subsystem is the **property listing process**.

This subsystem covers the process of advertising real estate properties, from registering property owners and properties, assigning agents, creating listings, adding listing images, and allowing clients to send inquiries related to specific listings.

The subsystem does not focus on contracts, payments, legal documentation, property visits, or sales transactions. Its scope is limited to the listing and advertising process.

---

## Entity Types

The selected entity types are:

1. **Agency** – represents a real estate agency.
2. **Agent** – represents an employee of the agency who creates property listings.
3. **Owner** – represents a person who owns one or more properties.
4. **Property** – represents a real estate property that can be advertised.
5. **Listing** – represents a published advertisement for a specific property.
6. **Image** – represents an image that belongs to a listing.
7. **Client** – represents a person who views listings and sends inquiries.
8. **Inquiry** – represents a message or request sent by a client for a specific listing.
9. **Category** – represents the type of property, such as apartment, house, land, garage, or commercial space.
10. **Location** – represents the geographical location of a property.

---

## Relationship Types

The selected relationship types are:

1. **owns** – connects Owner and Property.
2. **creates** – connects Agent and Listing.
3. **advertises** – connects Listing and Property.
4. **contains** – connects Listing and Image.
5. **sends** – connects Client and Inquiry.
6. **refers_to** – connects Inquiry and Listing.

Additional logical relationships are included in order to connect all selected entity types:

1. **employs** – connects Agency and Agent.
2. **classifies** – connects Category and Property.
3. **located_at** – connects Location and Property.

---

## Initial Tables

The database schema contains the following tables:

1. AGENCY
2. AGENT
3. OWNER
4. CATEGORY
5. LOCATION
6. PROPERTY
7. LISTING
8. IMAGE
9. CLIENT
10. INQUIRY

---

## Relationships Between Tables

- One agency can employ many agents.
- One agent belongs to exactly one agency.
- One owner can own many properties.
- One property belongs to exactly one owner.
- One category can classify many properties.
- One property belongs to exactly one category.
- One location can contain many properties.
- One property is located at exactly one location.
- One agent can create many listings.
- One listing is created by exactly one agent.
- One property can be advertised through one or more listings over time.
- One listing advertises exactly one property.
- One listing can contain many images.
- One image belongs to exactly one listing.
- One client can send many inquiries.
- One inquiry is sent by exactly one client.
- One listing can receive many inquiries.
- One inquiry refers to exactly one listing.

---

## Relationship Cardinalities

| Entity 1 | Relationship | Entity 2 | Cardinality | Description |
|---|---|---|---|---|
| AGENCY | employs | AGENT | AGENCY 0..N — AGENT 1..1 | One agency can employ multiple agents, while each agent belongs to one agency. |
| OWNER | owns | PROPERTY | OWNER 0..N — PROPERTY 1..1 | One owner can own multiple properties, while each property has one owner. |
| CATEGORY | classifies | PROPERTY | CATEGORY 0..N — PROPERTY 1..1 | One category can classify multiple properties, while each property belongs to one category. |
| LOCATION | located_at | PROPERTY | LOCATION 0..N — PROPERTY 1..1 | One location can be connected to multiple properties, while each property has one location. |
| AGENT | creates | LISTING | AGENT 0..N — LISTING 1..1 | One agent can create multiple listings, while each listing is created by one agent. |
| PROPERTY | advertises | LISTING | PROPERTY 0..N — LISTING 1..1 | One property can have multiple listings over time, while each listing advertises one property. |
| LISTING | contains | IMAGE | LISTING 0..N — IMAGE 1..1 | One listing can contain multiple images, while each image belongs to one listing. |
| CLIENT | sends | INQUIRY | CLIENT 0..N — INQUIRY 1..1 | One client can send multiple inquiries, while each inquiry is sent by one client. |
| LISTING | refers_to | INQUIRY | LISTING 0..N — INQUIRY 1..1 | One listing can receive multiple inquiries, while each inquiry refers to one listing. |

---

## Conceptual Schema

The conceptual schema is represented using an ER diagram. The ER diagram contains the selected entity types, their attributes, relationship types, and cardinalities.

The diagram shows the property listing process, where an owner owns a property, an agent creates a listing, the listing advertises a property and contains images, while clients send inquiries related to specific listings.

The ER diagram is stored in the following folder:

```text
diagrams/er-diagram.png
