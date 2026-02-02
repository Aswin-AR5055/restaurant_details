# Strapi Setup & Exploration (Task 1)

## Task Overview

The goal of this task was to:
- Clone the official Strapi repository
- Run Strapi locally
- Explore the project folder structure
- Start the Admin Panel
- Create a sample content type
- Add actual content
- Push the setup to GitHub
- Document the entire process
- Record a Loom video walkthrough

---

## Prerequisites

Ensure the following are installed on your system:

- Node.js (v18 or later recommended)
- npm or yarn
- Git

---

## Step 1: Clone the Official Strapi Repository

```bash
git clone https://github.com/strapi/strapi.git
cd strapi
```

This repository is the **Strapi monorepo**, which contains:
- Core Strapi packages
- Plugins
- Admin panel source
- Utilities and examples

**Note:**  
The Strapi monorepo is meant for **Strapi contributors and internal development** and is **not directly runnable** as an application.

---

## Step 2: Exploring the Folder Structure

Key directories explored:

- `packages/` → Core Strapi packages and plugins
- `packages/core/` → Main backend logic
- `packages/plugins/` → Official Strapi plugins
- `packages/admin/` → Admin panel source code
- `examples/` → Example projects
- `scripts/` → Build and helper scripts

This exploration helped understand how Strapi is structured internally.

---

## Step 3: Creating a Runnable Strapi Application

Since the monorepo itself cannot be run directly, a new Strapi project was created using the official CLI.

```bash
npx create-strapi-app@latest restaurant_details
cd my-strapi-app
npm run develop
```

This starts the Strapi development server.

---

## Step 4: Starting the Admin Panel

After running the project, the Admin Panel was accessed at:

```
http://localhost:1337/admin
```

An admin account was created to manage content and settings.

---

## Step 5: Creating a Sample Content Type

Using **Content-Type Builder** in the Admin Panel:

### Collection Type Created: `Restaurant` and `Category`

Fields added(Restaurant):
- `Name` (Text)
- `Description` (Rich Text)

The content type was saved and the server restarted when prompted.

Fields added(Category):
- `Name` (Text)
- Relation (many to many with restaurant)
---

## Step 6: Adding Actual Content

From **Content Manager**:
- Created One entry in Restaurant Collection
- Filled in Name and Description
- Created two categories in Category Collection
- Filled in category name and its relation with restaurant collection
- Published entries to make them available via API

---

## Step 7: Enabling Public API Access

By default, Strapi APIs are secured.

Steps followed:
- Settings → Users & Permissions Plugin
- Roles → Public
- Enabled:
  - `find`
  - `findOne` for both Restaurant and Category collection

This allowed public API access.

---

## Step 8: Verifying API Response

The content was successfully accessed using:

```
http://localhost:1337/api/restaurants
```

The API returned JSON data containing published blog entries.

---

## Step 9: Pushing to GitHub

```bash
git add .
git commit -m "Completed Strapi setup and created sample content type"
git push origin main
```

A Pull Request was created for review.

---

## Loom Video

A Loom video was recorded demonstrating:
- Repository cloning
- Folder structure exploration
- Running the Strapi app
- Admin Panel usage
- Content type creation
- Adding and fetching content via API

---

## Conclusion

This task provided hands-on experience with:
- Strapi architecture
- Headless CMS concepts
- Content modeling
- Role-based API permissions
- REST API consumption

---
