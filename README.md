# Populairy - Pop-up Event Organizer


> This app is at the beginning and constantly a work-in-progress.

---

🍿🥒🍅🥕🥮🍕🍰🥤🥢🥣🍱🌮🥐🥂📚🍵

**Populairy** is a pop-up event organizer to help running pop-ups smoothly.

Populairy = **Pop**-up + pop**ul**ar + **airy**

## 1. Background

Pop-ups became very popular worldwide since a few years and are an effective way for event hosts to save costs and to grow their networks and outreach. Pop-ups are enabled as a selling point within an existing event and/or space. While many self-made professionals rely on a regular income for them and their famillies pop-ups are also a great way for initiatives/groups/non-profits to collaborate in order to raise awareness and donations for a good cause.

When runnning a pop-up usually event hosts face challenges on:

- Venue Search => send inquiries, ask friends and partners, book venues
- Equipment / Products => build partnerships with suppliers to rent, buy or organize equipment, etc.
- Logistics => plan staff, delivery and pick-up
- Networking => research, handle feedback, outreach
- Marketing => word-of-mouth, social media, mailing lists, kitchen table

### Event types:

Examples

- Barber Shop
- Book Store
- Drinks
- Flash Tattoo
- Food
- Massage
- Tarot Reading
- Workshop (Repair | Bike | Sketch)
- Misc

## 2. Technical Requirements

- [x] NodeJS (Backend JS)
- [x] ExpressJS (Backend Framework)
- [x] MongoDB (Database)
- [x] Mongoose (Schema)
- [x] Pug (views) => be changed to React later
- [x] Nodemon (Dev Live Server)
- [x] Prettier (Formatting)
- [x] Axios (HTTP requests)
- [ ] Heroku || Netlify (Hosting)
- [ ] ReactJS (Frontend Framework)
- [ ] Babel (JS Compiler)
- [ ] Eslint (JS Linter)
- [ ] Mocha && Enzyme (Testing)

## 3. Features

- [ ] Task Manager
- [ ] Event calendar
- [ ] Addressbook
- [ ] Sign-up/Login
- [ ] Emailing
- [ ] Newsletter
- [ ] Solidarity pot
- [ ] Search

## 4. Data Model

### Event

- [ ] An event acts as a satellite event and can have one or more pop-ups.
- [ ] An event has 1 main host (eventHost) that can be a group or a person and is referenced to one or many pop-ups.
- [ ] An event can have multiple hosts (joinedHosts) that are confirmed as hosts.
- [ ] An event has a date with a day and time range (from, to) each.
- [ ] An event has a location with address, postcode, city and country info.
- [] An event has one or many guests attending.

### Pop-up

- [ ] A pop-up has 1 main organizer that can be a group or a person.
- [ ] A pop-up can have multiple organizers that are confirmed as organizers.
- [ ] A pop-up has the same location of an event that it joins (reference).
- [ ] A pop-up has the same date (day and time) is the same date of an event that it joins (reference).
- [ ] A pop-up can only have 1 main host that can be a group or a single person.
- [ ] A pop-up can only join 1 event (satellite) that it joins.
- [ ] A pop-up can have one or many guests subscribed from an event that it joins.

### User

- [ ] A user is by default a `guest` unless confirmed as an `event host` or `pop-up organizer`.
- [ ] A user can attend one event at a time.
- [ ] A user can attend one or many pop-ups of an event that the user subscribed for.
- [ ] A user can have one of these roles at a time:
	- guest
	- **Event**: main host (eventHost) || co-host (joinedHosts)
	- **Pop-up**: main organizer (organizer) || co-organizer (popupOrganizers)
- [ ] A user can act as a group or as a single person.
Offline / Before authentication:
- [ ] A first name, last name, email is required as a `guest`.
- [ ] A first name, last name, email and phone number is required as a Pop-up `organizer`.
- [ ] A first name, last name, email and phone number is required as an `event host`.


## Axios

## User

1. Get all useers

```js
axios.get('/user/all').then(console.log)
```

2. Get single user

```js
// GET http://localhost:3000/:id
axios.get('/user/5dd93e067689550c4a89fc03').then(console.log)
```

3. Create a new user

```js
// POST http://localhost:3000/user
axios.post('/user', {firstName: "Jonny", lastName: "Crush", email: "jonny@example.org"}).then(console.log)
```

4. Update single user

```js

// PATCH http://localhost:3000/user/:id
axios.patch('/user/5dd93e067689550c4a89fc03', {lastName: 'Another Lastname'}).then(console.log)
```

Delete a user
```js
// DEL http://localhost:3000/user/:id
axios.delete('/user/5dd92e87f94cd40612c0783d').then(console.log)
```


```

## Getting started

1. Select the week you want to setup, e.g. `week-4` and change into that directory.

```shell
$ cd week-4/
```

2. Install all npm packages

```shell
$ npm install
```

2. Copy `env.SAMPLE` and rename it to `.env` and make sure the `.env` file is listed in `.gitignore`.

```shell
$ cp env.SAMPLE .env
```

3. Start up the server:

```shell
# in dev mode with nodemon
$ npm run dev

# Dependent on your .env configs for NODE_ENV
$ npm start
```

4. Use prettier to format your code:

```shell
$ npm run format

# Prettify .pug files
$ ./node_modules/.bin/prettier --write "**/*.pug"
```