# intersections_redux
Jekyll implementation of the Inter/sections site

# How to use this repo:

1. Clone it locally. 
2. Make sure Jekyll and Bundler are installed.
Jekyll: `$ gem install jekyll`
Bundler: `$ gem install bundler`
GH Pages: `$ gem install github-pages`
(Error messages are usually for outdated versions of Ruby and will tell you how to update it.)
3. Navigate to the root of the repo.
4. Type this:
`$ jekyll serve`

Watch the command line as it compiles the site and starts the server.
This will start the site at `localhost:4000` when it's ready.

Ask Astrid or Tom for help if things are not working properly.

# The structure:

## The bones

Each link across the top has a partner html file in the root of the repo. These are currently:

`index.html
about.html
exhibition.html
syposium.html
events.html
location.html`

These are the pages that are served when each of the links at the top are clicked.

## The _data file

In here are files of data that can be pulled into specific sections of the site. For instance, all the Speaker info is together, so we can just edit that one file and have it all pulled in neatly. Data files are great!

Currently served from this directory:

Supporters - This is the link to supporter images for display, and a URL for each
Speakers - This will be the info about our Symposium speakers
Artists - This will be the profile of our artists
Nav - This is the navigation links across the top.
Events - The information for the events listed on the page. Will soon link to associated posts for each one.

### How to use stuff in the data file

You can make new data structures for whatever you want. To use them, you will probably want to loop over every item in the file, which you do like this:

`{% for event in site.data.events %}`

This tells Jekyll "Inside the _data file at the root of the site, there's a yml file called events. Go into that, and look at each item (which I'll refer to as 'event')."

Then, you can manipulate data inside each item, for example by grabbing the associated picture:

`<img src="{{event.image}}">`

Notice that you usually have to put the quote marks around the info yourself to make HTML happy.

## The _includes file

Includes are little slices of HTML that you can swap in and out of your layout. They're located in the _includes file.

### How to use includes

In an html document, you can type this to bring in the content of an include file:

`{% include name-of-the-include-here.html %}`

When it sees the command *include*, Jekyll goes to that file and tries to find the partial.

## Difference between data and includes

Includes are for layout elements. 

Data files are for plain data. You might style this within an include element, but it has no style of its own.

## Making changes

I really like Jekyll because it watches my directory, and when I make changes and refresh the page the changes are reflected. The only time you'll have to restart the server is when you make changes to the config.yml file (which you shouldn't need to do since it's not super important in this theme).

If you make changes and they're not reflected, check the command line - often it's because you've moved or renamed something and Jekyll is trying to give you an error but you aren't paying attention.

## To Do

- Make this site a clear and accurate reflection of Inter/sections that is simple to navigate.

# Hosting

The site is hosted on Github pages. The domain registrar is GoDaddy, and the DNS and SSL certificate are managed by Cloudflare. Contact Tom if you need more details about these.
