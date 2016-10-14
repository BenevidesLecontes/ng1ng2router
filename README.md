# Migrating Angular 1 Applications to Angular 2 Using NgUpgrade and Angular Router;

## How to Run

- clone this repo
- `npm install`
- `rm node_modules/@angular/router`
- `npm install angular-router-3.1.0.tgz`
- `npm start`
- open `localhost:8080`

- optionally `npm run build` to build bundle

## Applicaiton

### Modules

The application has three modules:

* Main Menu
* Messages
* Settings

They illustrate the three stages of migrating modules from Angular 1 to Angular 2.

* The Main Menu moduule is written in Angular 1. In other words, the migration of this module hasn't started yet.
* The Messages module is written using Angular 1, but one of its components has been migrated to Angular 2.
* The Settings module is written using Angular 1. In other words, the migration of this module has been completed.

Every module defintes components, services, and routes. In addition every module has an NgModule with a static methods where we can downgrade/upgrade, components and services.


### Routes

These are the routes the application supports:

* /id
* /messages/:folder
* /messages/:folder/:id
* /settings
* /settings/pagesize

The first three routes are handled by the Angular 1 router, and the last two are handled by the Angular 2 router. We define a custom UrlHandlingStrategy to partition all URLs into these two sets.


### Wiring it Up

See comments in `app.ts` and `upgrade_utils.ts`.