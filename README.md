# UNIHIKER Documentation 
The source code of the documentation hosted at [www.unihiker.com/wiki/](https://www.unihiker.com/wiki/)

## Host the documentation locally

1. **Install Software**
    - Python3
    - Git

2. **Install mkdocs and mkdocs-material**
    ```bash
    python -m pip install mkdocs mkdocs-material mkdocs-minify-plugin mkdocs-glightbox
    ```
    If already installed, you can upgrade them:
    ```bash
    python -m pip install --upgrade mkdocs mkdocs-material mkdocs-minify-plugin mkdocs-glightbox
    ```
3. **Clone the Repository**

    ```bash
    git clone https://github.com/UNIHIKER/unihiker-docs.git
    ```

4. **Navigate to the cloned repository's path** in the command line (where you can see the `mkdocs.yml` file), and run the local mkdocs test server:
    ```bash
      
   python -m mkdocs serve -a 127.0.0.1:8000
   
   ```
5. **Access the local test server** using a web browser by visiting [127.0.0.1:8000](http://127.0.0.1:8000/).

## How to Contribute
We welcome any contributions you can provide, such as:

- Edits to improve our grammar or fix any typos
- Edits to improve the clarity of any instructions
- Additional annotated examples for others to follow
- And much more! - Anything that you think would be good to add for the growth of this community is greatly appreciated

Making a contribution is as simple as forking this repository, making edits to your fork, and contributing those edits as a pull request. For more information on how to make a pull request, see [Github's documentation](https://help.github.com/articles/using-pull-requests/).