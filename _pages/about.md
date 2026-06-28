---
permalink: /
title: "Welcome"
browser_title: "Xuepeng Wang"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a Ph.D candidate in theoretical condensed matter physics at <a href="https://physics.cornell.edu/" style="text-decoration: none;">Cornell</a>. I am fortunate to be advised by <a href="https://www.chowdhury.lassp.cornell.edu" style="text-decoration: none;">Prof. Debanjan Chowdhury</a>. I work on strongly correlated electronic systems, using a combination of analytical approach (e.g. large-N field theory) and numerical simulations (e.g. quantum Monte-Carlo)

Research Interests
======
Unlike Monte-Carlo, my research interests diverge. Specifically, I am interested in
- **Non-Fermi Lquids & Strange metals**: including their spectral properties, transport and collective excitations.
- **Moiré materials**: including their unconventional superconductivity, exotic composite excitations, correlated topological phases, intertwined orders and quantum phase transitions.
- **Numerical techniques**: including Determinant Quantum Monte-Carlo, and Green's function compression techniques such as discrete Lehmann representations.
- **Quantum algorithms**: including Hamiltonian simulation by qubitization, state tomography and state preparation.

In the past, I also did density functional theory calculations. I will also be interested in working on generative-model-inspired/assisted numerical methods.

Contact
======
Email: xw577-at-cornell-dot-edu

<section class="mobile-publications">
  <h1 class="mobile-publications__title">
    Publications
    {% if site.author.googlescholar %}
      <a class="mobile-publications__scholar-button" href="{{ site.author.googlescholar }}">Google Scholar</a>
    {% endif %}
  </h1>
  <div class="wordwrap publications__intro">
    *: equal contribution; # corresponding author.
  </div>

  {% if site.publication_category %}
    {% for category in site.publication_category %}
      {% assign title_shown = false %}
      {% for post in site.publications reversed %}
        {% if post.category != category[0] %}
          {% continue %}
        {% endif %}
        {% unless title_shown %}
          <h3 class="publications__category-title">{{ category[1].title }}</h3>
          {% assign title_shown = true %}
        {% endunless %}
        {% capture publication_item_class %}{% cycle 'home_publication_rows': 'publication__item--shaded', 'publication__item--transparent' %}{% endcapture %}
        {% include archive-single.html item_class=publication_item_class %}
      {% endfor %}
    {% endfor %}
  {% else %}
    {% for post in site.publications reversed %}
      {% capture publication_item_class %}{% cycle 'home_publication_rows': 'publication__item--shaded', 'publication__item--transparent' %}{% endcapture %}
      {% include archive-single.html item_class=publication_item_class %}
    {% endfor %}
  {% endif %}
</section>

Fun
======
Outside of research, I enjoy skiing, playing <a href="https://www.instagram.com/p/DNQZDUWuOPfZK-QQ8Mwk_f_NHAmK41Bi0LQ82o0/" style="text-decoration: none;">piano</a> and video gaming. My gaming interests also diverge, including Civ6, Splatoon etc.

<!-- Many of the features of dynamic content management systems (like Wordpress) can be achieved in this fashion, using a fraction of the computational resources and with far less vulnerability to hacking and DDoSing. You can also modify the theme to your heart's content without touching the content of your site. If you get to a point where you've broken something in Jekyll/HTML/CSS beyond repair, your Markdown files describing your talks, publications, etc. are safe. You can rollback the changes or even delete the repository and start over - just be sure to save the Markdown files! You can also write scripts that process the structured data on the site, such as [this one](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb) that analyzes metadata in pages about talks to display [a map of every location you've given a talk](https://academicpages.github.io/talkmap.html).

For those users that need more advanced functionality, the template also supports the following popular tools:
- [MathJax](https://www.mathjax.org/) for mathematical equations
- [Mermaid](https://mermaid.js.org/) for diagraming
- [Plotly](https://plotly.com/javascript/) for plotting

Getting started
======
1. Register a GitHub account if you don't have one and confirm your e-mail (required!)
1. Fork [this template](https://github.com/academicpages/academicpages.github.io) by clicking the "Use this template" button in the top right. 
1. Go to the repository's settings (rightmost item in the tabs that start with "Code", should be below "Unwatch"). Rename the repository "[your GitHub username].github.io", which will also be your website's URL.
1. Set site-wide configuration and create content & metadata (see below -- also see [this set of diffs](https://archive.is/3TPas) showing what files were changed to set up [an example site](https://getorg-testacct.github.io) for a user with the username "getorg-testacct")
1. Upload any files (like PDFs, .zip files, etc.) to the files/ directory. They will appear at https://[your GitHub username].github.io/files/example.pdf.  
1. Check status by going to the repository settings, in the "GitHub pages" section

Site-wide configuration
------
The main configuration file for the site is in the base directory in [_config.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_config.yml), which defines the content in the sidebars and other site-wide features. You will need to replace the default variables with ones about yourself and your site's github repository. The configuration file for the top menu is in [_data/navigation.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_data/navigation.yml). For example, if you don't have a portfolio or blog posts, you can remove those items from that navigation.yml file to remove them from the header. 

Create content & metadata
------
For site content, there is one Markdown file for each type of content, which are stored in directories like _publications, _talks, _posts, _teaching, or _pages. For example, each talk is a Markdown file in the [_talks directory](https://github.com/academicpages/academicpages.github.io/tree/master/_talks). At the top of each Markdown file is structured data in YAML about the talk, which the theme will parse to do lots of cool stuff. The same structured data about a talk is used to generate the list of talks on the [Talks page](https://academicpages.github.io/talks), each [individual page](https://academicpages.github.io/talks/2012-03-01-talk-1) for specific talks, the talks section for the [CV page](https://academicpages.github.io/cv), and the [map of places you've given a talk](https://academicpages.github.io/talkmap.html) (if you run this [python file](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.py) or [Jupyter notebook](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb), which creates the HTML for the map based on the contents of the _talks directory).

**Markdown generator**

The repository includes [a set of Jupyter notebooks](https://github.com/academicpages/academicpages.github.io/tree/master/markdown_generator
) that converts a CSV containing structured data about talks or presentations into individual Markdown files that will be properly formatted for the Academic Pages template. The sample CSVs in that directory are the ones I used to create my own personal website at stuartgeiger.com. My usual workflow is that I keep a spreadsheet of my publications and talks, then run the code in these notebooks to generate the Markdown files, then commit and push them to the GitHub repository.

How to edit your site's GitHub repository
------
Many people use a git client to create files on their local computer and then push them to GitHub's servers. If you are not familiar with git, you can directly edit these configuration and Markdown files directly in the github.com interface. Navigate to a file (like [this one](https://github.com/academicpages/academicpages.github.io/blob/master/_talks/2012-03-01-talk-1.md) and click the pencil icon in the top right of the content preview (to the right of the "Raw | Blame | History" buttons). You can delete a file by clicking the trashcan icon to the right of the pencil icon. You can also create new files or upload files by navigating to a directory and clicking the "Create new file" or "Upload files" buttons. 

Example: editing a Markdown file for a talk
![Editing a Markdown file for a talk](/images/editing-talk.png)

For more info
------
More info about configuring Academic Pages can be found in [the guide](https://academicpages.github.io/markdown/), the [growing wiki](https://github.com/academicpages/academicpages.github.io/wiki), and you can always [ask a question on GitHub](https://github.com/academicpages/academicpages.github.io/discussions). The [guides for the Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) (which this theme was forked from) might also be helpful. -->
