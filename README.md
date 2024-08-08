<h1 align="center" style="border-bottom: none;">🚀 Literature Survey for EDC</h1>

Welcome to Literature Survey for team EDC! 📚✨ This repository is built on top of [literature survey template](https://github.com/VirtualPatientEngine/literatureSurvey) developed by [Team VPE](https://bio.mx/research-teams/artificial-intelligence/team-vpe/) using Semantic Scholar's [Recommendation API](https://api.semanticscholar.org/api-docs/recommendations).

### Index
1. [Recommendation types](#recommendations-types)
2. [Usage](#usage)
3. [Getting Started for Non developers](#getting-started-for-non-developers)
4. [Getting Started for developers](#getting-started-for-developers)
5. [Bugs or Feature Requests](#bugs-or-feature-requests)

### Recommendations types
Semantic Scholar provides 2 types of recommendations:

1. ```Single-paper recommendations```: Each article you provide will be used to generate recommendations specifically for that article.
2. ```List-based recommendations```: Articles related to a topic will be selected as positive articles. Negative articles will be selected by considering all articles from other topics. These positive and negative articles will be used to retrieve recommendations from Semantic Scholar.

### Usage
You can easily customize it to your own fields of interest by following the steps outlined below. To see how the automated literature survey repo looks like, visit [Team VPE's GitHub website](https://virtualpatientengine.github.io/literatureSurvey).

### Getting Started for Non Developers
_Jump to the next section if you are a developer_
1. Prepare a ```query.tsv``` file with 3 columns: Under the `Title` column, give titles to your topics. Under the `Use` column, write <kbd>1</kbd> if you want to use the article for recommendations or <kbd>0</kbd> if you just want to display the article. Under the `URL` column, specify the corresponding URLs to [Semantic Scholar](https://www.semanticscholar.org/) article.

2. Navigate to the data folder by clicking ```app > data``` on the GitHub page.
![alt text](img/image.png)

3. Click on the dropdown `Add file` followed by ```Upload files``` buttons.
![alt text](img/image-1.png)

4. Upload the ```query.tsv``` file that you have prepared. Under the header ```Commit changes```, in the first field (_Add files via upload_), type ***feat: new query.tsv***, and press the blue-colored ```Commit changes``` button at the bottom of the page.

5. This will trigger a workflow to update the literature survey, and can take a few minutes. You should be able to see a brown-colored circle on your main GitHub page. This means that the workflow is still running.
![alt text](img/image-2.png)

### Getting Started for Developers

1. Open up the ```app/data/query.tsv``` file in your favorite code editor or Excel.

2. Under the `Title` column, give titles to your topics. Under the `Use` column, write <kbd>1</kbd> if you want to use the article for recommendations or <kbd>0</kbd> if you just want to display the article. **Under the URL column, specify the corresponding URLs to [Semantic Scholar](https://www.semanticscholar.org/) article.** Submit your edited file by clicking on `Commit changes...`. In the `Commit message` add a prefix by using one of these keywords **feat:, fix: or chore:**, e.g., "feat: added one paper". After committing changes to the `main` branch directly, the workflows should start automatically.

3. (Optional) Create a venv:
```
> python -m venv env
# On Windows
> .\env\Scripts\activate

# On macOS and Linux
> source env/bin/activate
```

4. (Optional) Install all the necessary requirements:
```
> pip3 install -r requirements.txt
```

5. (Optional) It's time to fetch some literature! Run the ```literature_fetch_recommendation_api.py``` script to grab the recommended articles from Semantic Scholar:
```
> cd app/code
> python3 literature_fetch_recommendation_api.py
```

6. (Optional) Now, fire up MkDocs locally to view the recommended articles:
```
> mkdocs serve
```
Head over to the localhost link that pops up in your terminal. 

7. This repository includes a `mkdocs-deploy.yml` [workflow](https://github.com/VirtualPatientEngine/literatureSurvey/blob/main/.github/workflows/mkdocs-deploy.yml) that uses GitHub Actions to automatically execute the specified script **once a week** and deploy the literature survey system as a [GitHub Pages website](https://virtualpatientengine.github.io/literatureSurvey/). Feel free to edit to based on your project needs or use it as it is.

> To host your literature survey system online, you must place the YML file in the `.github/workflows/` folder. Once you have pushed you code to GitHub, under the [Actions](https://github.com/VirtualPatientEngine/literatureSurvey/actions) tab, you'll find the ongoing `mkdocs-deploy.yml` workflow (this might take even 1h or more depending on the current workload of compute servers and length of the publication list). Once this workflow finishes, head over to the [Settings/Pages](https://github.com/VirtualPatientEngine/literatureSurvey/settings/pages) tab. From there, choose `Deploy from a branch` in the Source section. Under the Branch subsection, select `gh-pages` and root from the dropdown menus, then click `Save`.

8. Under `About` section of your repository, head to the gear symbol and check the box `Use your GitHub Pages website` and `Save changes`. You will see an URL to your literature survey repository under `About` section of the `Code` tab. 

9. Change <kbd>site_url</kbd>, <kbd>theme:/logo:</kbd>, <kbd>repo_url</kbd>, and <kbd>repo_name</kbd> in ```base.yml``` to the values related to your project.

10. If you'd like to edit the home page of the website, head over to `docs/index.md` to make the changes.

11. (Optional) Edit custom.css if you'd like to change the styling of web pages.

### Bugs or Feature Requests
If you encounter any bugs or have brilliant ideas for new features, please head over to the [Issues](https://github.com/VirtualPatientEngine/literatureSurvey/issues) and let Team VPE know.

### Happy surveying! 📖🔍
