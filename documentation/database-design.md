# Database Design

## Project Topic

The project represents an information system for a real estate agency.

## Selected Subsystem

The selected subsystem is the property listing process.

This subsystem covers the process of advertising real estate properties, from registering property owners and properties, assigning agents, creating listings, adding listing images, and allowing clients to send inquiries related to specific listings.

## Entity Types

The selected entity types are:

- Agency
- Agent
- Owner
- Property
- Listing
- Image
- Client
- Inquiry
- Category
- Location

## Relationship Types

The selected relationship types are:

- Owner owns Property
- Agent creates Listing
- Listing advertises Property
- Listing contains Image
- Client sends Inquiry
- Inquiry refers to Listing

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

## Relationships Between Tables

- One agency can have many agents.
- One owner can own many properties.
- One category can contain many properties.
- One location can contain many properties.
- One agent can create many listings.
- One property can be advertised through one or more listings.
- One listing can contain many images.
- One client can send many inquiries.
- One inquiry refers to one listing.

## Relational Model Draft

AGENCY(agency_id PK, name, tax_number, phone, email, address)

AGENT(agent_id PK, first_name, last_name, phone, email, agency_id FK)

OWNER(owner_id PK, first_name, last_name, phone, email)

CATEGORY(category_id PK, name, description)

LOCATION(location_id PK, city, municipality, street, street_number)

PROPERTY(property_id PK, title, area, room_count, price, status, owner_id FK, category_id FK, location_id FK)

LISTING(listing_id PK, title, description, listing_date, expiration_date, status, property_id FK, agent_id FK)

IMAGE(image_id PK, image_url, description, listing_id FK)

CLIENT(client_id PK, first_name, last_name, phone, email)

INQUIRY(inquiry_id PK, inquiry_date, message, status, client_id FK, listing_id FK)