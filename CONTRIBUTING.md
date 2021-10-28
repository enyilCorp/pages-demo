# GitHub Handbook Content

The GitHub Handbook website is a [Jekyll static site](https://jekyllrb.com/).

Most of the content is editable as regular Markdown in files inside the ```_pages``` folder.

If you want to modify HTML (e.g., create new pages that show in a sidebar), and you're not familiar with Jekyll, you'll want to ask a developer to help you.

<details>
<summary>Configuration Variables</summary>
<br>

Update the following variables to customize this site to your organization:

<details>
<summary><code>_config.yml</code></summary>
<br>

Update the values for the following variable groups:

- <code>contact-handbook</code>
- <code>org</code>
- <code>support</code>
- <code>slack</code>
- <code>conical_domain</code>
- <code>url</code>
- <code>baseurl</code>
- <code>custom</code>

</details>
</br>

<details>
<summary><code>_main.scss</code></summary>
<br>

Update the following to change the logo image:

<code>.usa-hero {  
    background-image:</code>

Image file is saved here:

<code>/docs/assets/img/logo/github-handbook.png</code>

</details>
</br>

</details>
</br>

<details>
<summary>Where Things Live</summary>
<br>

* ```_data``` - simple .yml files containing data that is read into other pages

* ```_includes``` - small pieces of HTML that are included into other pages, e.g., the header, the footer, etc.

* ```_layouts``` - HTML structures for each page type:
  * ```base``` - the basic HTML structure for all pages
  * ```home``` - the HTML structure for the Home page
  * ```jump-menu``` - the HTML structure for pages with a right side jump-down menu
  * ```no-sidebar``` - the HTML structure for pages that do not have a sidebar, e.g., the contact page
  * ```page``` - the HTML structure for pages with a sidebar  

* ```_posts``` - announcements that appear on the site

* ```_sass``` - the uncompiled/editable CSS files

* ```assets``` - the public assets folder for images, CSS, JS, etc

* ```Gemfile``` and ```Gemfile.lock``` - no need to update unless you add new Gems

* ```_config.yml``` - the file containing configuration information for Jekyll

* ```manifest.json``` - the manifest file for mobile icons

</details>
</br>

<!-- markdownlint-disable -->
<details>
<summary>Page Structure</summary>
<br>

### General

All editable site pages live in the ```_pages``` folder.

### Home page

* The Home page is a custom page with its own layout -- ```_layouts/home.html```.

* Most of the content is editable as [Jekyll front matter](https://jekyllrb.com/docs/front-matter/) in the ```_pages/index.md``` file.

* Other editable content is noted in the Jekyll front matter in the same file.

### Pages with Sidebars

* Pages in the Delivery Guide and Resources section contain a sidebar and use the ```_layouts/page.html``` layout.

* These pages are more complex, for example, they may use an include for secondary navigation or to include small bits of HTML.
  * You can see where these pieces are included in the page file. For example, in the ```_pages/delivery/build-and-test-1.md``` file, you'll see ```{% include phase-planning.html phase="Build and Test" %}```. This says "include the ```_includes/phase-resources.html``` HTML and note the phase as *build and test*."
    * Inside the ```_includes/phase-resources.html``` file, you'll see ```{{ site.data.phase-resources.guides | markdownify }}```. This says "include the content in the *guides* section of the ```_data/phase-resources``` file.

* Most of the content is editable as Markdown below the three dashes (```---```) in the relevant ```_pages``` files, e.g., the ```_pages/delivery/build-and-test-1.md``` file.

### Miscellaneous Pages

> Contact and 404

* These pages use the ```_layouts/no-sidebar.html``` layout.

* Most of the content is editable as Markdown below the three dashes (```---```) in the relevant ```_pages``` files, e.g., the ```_pages/contact.md``` file.

* Other editable content is noted in the Jekyll front matter in the same file.

</details>
</br>

<details>
<summary>Using Markdown in Content</summary>
<br>

### General

You can use Markdown as normal in ```_pages``` files below the three dashes (```---```). E.g., paragraphs, bullet points, etc.

The ```_sass/main.scss``` file styles all the Markdown.

There is a special CSS style for a blockquote, which you can use by typing ```> content goes here``` in your Markdown. For example,
> This is not a fancy blockquote.

Markdown is not allowed in Jekyll front matter (the content between the three dashes (```---```).

* If you need to style something in front matter, you'll need to use regular HTML tags.

### Links

To create links to pages inside the Handbook, use this format:

* ```[User research guide]({{site.baseurl}}/resources/user-research)```
  * The ```{{site.baseurl}}``` portion helps Jekyll create the proper link.

To create links to pages outside the Handbook, use offsite links in this format:

* ```<a target="_blank" href="{{ site.baseurl }}/resources/more/checkpoint">```
  * This opens the link in a new tab/page.

</details>
</br>

<!-- markdownlint-restore -->
