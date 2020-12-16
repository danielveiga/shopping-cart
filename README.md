# [Beta] Aurabox Playground

Aurabox Playground (monorepo) where lies all latest tooling and frameworks to build digital products

## 📋 Minimum Requirements

- node >= 12.0.0 - [nodejs.org](https://nodejs.org/)
- yarn >= 1.22.0 - [yarnpkg.com](https://yarnpkg.com/getting-started/install)
- expo >= 3.0.0 - [docs.expo.io](https://docs.expo.io)

Are you on linux, mac or wsl? Have your heard of [**asdf**](https://asdf-vm.com)? Google it...

If you find it good, so, do you will for [**direnv**](https://direnv.net/)

Thank us later. 👍

## 🚀 Getting Started

```sh
# install dependencies
yarn install

# start dev
yarn develop

# watch for tests
yarn test:watch
```

### Additional step for strapi apps

1) generate a UUID v4
https://www.uuidgenerator.net/version4

2) past into strapi/package.json like this

```json
"strapi": {
  "uuid": "PAST_YOUR_UUID_HERE"
},
```

## 📖 Understanding

Firstly, let's have look over the folders structure so you understand and get more confident to work with.

```
/apps           <--- Some app samples
  /expo         <--- React Native Expo
  /appflutter   <--- Flutter app, run your own
  /neutron      <--- React SPA with duck pattern (redux, saga)
  /nextjs       <--- NextJS (SSR) for SEO friendly apps/websites
  /nestjs       <--- NEST (not Next) for API (recommended)
  /strapi       <--- Strapi for APIs with builtin backoffice

  ############# OVER CONSIDERATIONS #############
  /netcore   <--- NetCore API (if you want too)
  /spring    <--- SpringBoot (why not? that's democracy)

/pkgs        <--- Shared libraries
  /ds        <--- Design System (all sharable components)

  ############# OVER CONSIDERATIONS #############
  /core      <--- Frontend (axios, redux - ducks, saga)
  /utils     <--- Frontend (data manipulation, parsers, etc)
```

If you don't find some, maybe it was recently removed (even no one minded to remove from here still), or maybe it didn't even was added, but its on the way to be added.


Please let us remind you to take a look over the project yourself before playing with it, see how are files are structured, which apps and packages are available by now -- no need to be outdated with docs showing it (:

Just keep in mind that we recommend you to set your common packages (used by apps) on /pkgs

## ⚙️ Configure

Then now its time to setup your needs, choose which apps will your use.

When you are ready, add them to package.workspaces so yarn can install in use workspaces only dependencies.

There is 2 ways to achieve it.

**FIRST WAY (Recommended for wannabe real projects)**

Easy one, remove what you don't need from /apps and /pkgs.

Then, set those dirs with wildcard on package.json.

```json
// packages.json
...
"workspaces": [
   "apps/*",
   "pkgs/*",
]
...
```

or you may go with the second...

**SECOND WAY (Recommended if just playing)**

No need to remove nothing, just add strict used workspaces.

```json
// packages.json
...
"workspaces": [
   "apps/app1",
   "apps/app2",
   "apps/app3",
   "pkgs/pkg1",
   "pkgs/pkg2",
]
...
```

Both ways you going to install only needed third party dependencies.

You can now duplicate an app or pkg to fit your needs, rename its directory and package.name and update your root scripts.

## 🐛 TROUBLESHOOTING

If you change something after first install, maybe workspaces did make a mess with dependencies and you get some failure running package scripts, specially if you running React Native app.

**TO FIX IT** - So, you may:

### Remove npm packages
```sh
# on linux, mac, wsl
rm -rf node_modules

# old friend windows
rmdir node_modules /s /q
```

## 🏁 Roadmap

## Urgent

- [x] move local husky, formatter and linters (neutron)

### Apps

- [ ] set expo, neutron, next typescript enabled
- [ ] add common used scripts to needed

### Pkgs

- [ ] build the react designsystem with post

### DX - Developer Experience

- [ ] set resolutions on root package to solve dependencies
- [ ] eslint for linting
- [ ] prettier for formatting (watch for eslint colision)
- [ ] husky for DX (a step for lint and prettier in commiting)
- [ ] .vscode files
- [x] create docker-compose
- [ ] improve readme documentation - docker, etc

### Test

- [ ] set test tooling for project
