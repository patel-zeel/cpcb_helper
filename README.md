# cpcb_helper

## Method 1 (Latest)
### Steps
#### `another_method.ipynb`
- In this method, we directly scrap the data from the CPCB website which does not require any Captcha solving. We use headless selenium to automatically fill the form for each station and download the year-wise CSV files. 
- This is a full-proof method since we do not do any pattern mathcing for URLs and directly download the dynamically retrived URLs.

#### `scrap_lat_lon.ipynb`
- This notebook helps scrapping coordinates of all the stations from the CPCB website. A manual Captcha solving is needed in the beginning and whenever the Captcha is asked again.

#### `combiner.ipynb`
- This notebook does a bit of preprocessing and saves the data in a desired format (NetCDF).

## Method 2
### Steps
#### `get_site_IDs.ipynb`
- Follow the instructions in the notebook to get the site IDs for all the CPCB CAAQMS. This will save the site IDs in a file called `site_ids.csv` in the `code` directory. `site_ids.csv` is .gitignored so it won't be pushed to the repository. This is done to avoid any conflicts with CPCB's data policy.
- You'll need to manually go to the browser opened by selenium, solve a captcha and then further proceed with the next cell execution. 
- This step has to be done interactively so if you are using a non-GUI environment, you can complete this step locally on your GUI machine since it is cheap and will take only seconds to run.
#### `download.ipynb`
- This will download the data from the CPCB website and save it in the `files` directory. This may take a few minutes to few hours depending on the network speed and amount of parallelization. 
- I ran it on 32 cores without giving a pause and CPCB didn't block my IP but this is not recommended.
- This is not the full-proof method in case where the download URLs do not match the pattern we think they have.x