# Homepage of the TSMEAN Project (an example of an AMP page)

This is the code the tsmean tutorial page at https://www.tsmean.com is built with.

This repository isn't interesting if you're interested in building a MEAN
application. If you're interested in how to build a a MEAN application visit the actual page at
https://www.tsmean.com. If, however, you think the
tsmean.com page has an awesome layout, loads really fast, or is somehow else
interesting and you'd like to build a page just like it, you've come to the right place.

The tsmean.com page is built with AMP. AMP stands for Accelerated Mobile Pages
and is a framework for super-fast loading pages.

## Install & Run

```
git clone https://github.com/bersling/tsmean-amp.git my-project #replace my-project with your project's name
cd my-project
npm install #installs the required packages
npm run build #builds the build
npm start #starts a server
```

## Project structure

To get an overview of what you'll be working with, here's the structure:

```
tsmean-amp/
├── app/
│   ├── components/ # here are reusable UI elements for your app
│   │   ├── some-component/
│   │   │   ├── some-component.html
│   │   │   └── some-component.scss
│   │   └── ... # more components
│   ├── pages/ #here go pages of your app (e.g. /about)
│   │   ├── index.html # the root page
│   │   ├── ... # more pages
│   │   ├── category1/ # pages that will be available on /category1
│   │   │   ├── page1.html # will be on /category/page1
│   │   │   ├── page2.html
│   │   │   └── ... # more pages
│   │   └── ... # more categories
│   └── styles/ # here go styles that don't belong to a component
│       ├── styles.scss # the root of your scss
│       ├── button.scss # styling your buttons...
│       └── ... # even more styles
├── img/ # all images
├── dist/ # auto-generated folder that holds the compiled sources
├── node_modules/ # auto-generated folder that holds the node_modules
├── README.md # what you're currently reading
├── deploy.sh # deploy script, adjust to your needs...
├── package.json # definition of all "npm" commands & packages that are required
├── server.ts # small server to test app locally
├── yarn.lock # auto-generated, ensures the same packages are installed for all yarn users.
├── .gitignore # files being ignored from git
└── compile.ts # part of the build process
```



## Development

### Running a server
You can run a local server for development using
```
npm start
```
Now you should have a server running at port 8082. You'll just do this at the start of each development session. If you're heading ofer to http://localhost:8082, you'll find what the server is serving. If you've built the project, it should display the landing page.


### Rebuilding when you changed something
To rebuild the project, after you've modified html or scss files or after you've added images to the img directory (or after any changes at all), run:

```
npm run build
```
This executes the "build" command in "scripts" in the `package.json` file.

### Changing the html
Html is divided into two groups: pages and components. Pages are e.g. /about or /home. Components are things you want to **reuse**, for example `footer.html` which you'll use on every page. After changes, run `npm run build`.

### Changing the styles (css / scss)

Scss is sass, which is a precompiler for css to write more modular css. It's actually pretty easy to learn, you'll get the basics in 10 minutes by reading: http://sass-lang.com/guide

If styles are for a specific component, put them in the same folder as the html. **You'll have to register/import all .scss files in styles.scss!**

If they are general-purpose styles, put them in the styles folder at a matching position.

After changes, run `npm run build`.


### AMP

Since it's an AMP project, you'll have to be careful to follow the rules
of AMP. For instance, in an AMP project you're not allowed to use
the `<img>` tag. You'll have to use the `<amp-img>` tag. If you don't follow those rules
your page doesn't break, it just doesn't get the "AMP-SEO Bonus" anymore. During the build process, it logs to the console whether each page passes amp validation or not.

AMP has a lot of predefined components and a pretty good documentation you can find at https://www.ampproject.org/ and you'll find examples for all components at https://ampbyexample.com/.


