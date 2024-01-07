# deets-website
Code for the deets project website. 

## Contribution Guide
### Installing Jupyter-book
This repository is public, so you can make modifications to this project. 

This project is made using [jupyter-books](https://jupyterbook.org/en/stable/intro.html). Jupyter-books is a python module that converts markdown and jupyter notebooks into a website as shown at ______________________

1. Follow the instructions [here](https://jupyterbook.org/en/stable/start/overview.html) to install jupyter-book.

*If you are experienced with GitHub*

- Clone this repo
- Make the modifications you'd like

  *If you are new to GitHub*
- Install GitHub Desktop
- In this repo, hit Code > Open with [Github Desktop](https://desktop.github.com/). This should download the repo files and you can modify them.

### Contributing pages
If you'd like to contribute a new page, you'll need to learn the basics of markdown. Here's a tutorial you can follow: https://www.geeksforgeeks.org/introduction-to-markdown/.

- Open the file `yay_python/_toc.yml`
- At the bottom of the file, add `- file: fileName` (change `fileName` to whatever you want :) )
- Create a file called `fileName.md` or `fileName.ipynb`.
- Type up your content in those files. A `.md` is a markdown file, and a `.ipynb` is a [jupyter notebook](https://jupyter.org/).
- Run `jupyter-book build yay_python/` in the directory where `yay_python/` is stored
- To view the webpage output, go to the directory `yay_python/_book/`. This is where all the `html` files are stored. Click on `fileName.html` to view the page you made. 

### Uploading your changes
- In GitHub Desktop, commit the changes and select "push to origin"
- [ ] add photo to show this
- Once your changes appear on GitHub, run the following command in command line where the `_book/` directory is stored on your computer
  ```
  ghp-import -n -p -f _book/html
  ```

 
## Todo List/Known Issues
- [ ] Remove markdown.md file and `- file: markdown` from `_toc.yml`. Website breaks for some reason if I try removing it :/.
- [ ] Finish website content. 
- [ ] Play with website CSS (default colour scheme is a bit boring)

## Contact us
For any questions, please contact us on Discord @ assistant_of_milo or by email @ 340895069@gapps.yrdsb.ca
