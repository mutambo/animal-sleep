# Animal Sleep

A small exploratory project that examines the relationship between average sleep duration and body mass across 77 animal species. This repository contains a Jupyter notebook (animal_sleep.ipynb), the dataset (animal-sleep.csv), and a small helper module (`linear_model.py`) used in the notebook to fit and visualize simple linear models.

Description
-----------
The dataset provides average hours of sleep per day for a variety of animal species together with each species' average body mass (in kg) and diet category (carnivore, omnivore, herbivore). The main goals of the notebook are:

- Explore the relationship between body mass and sleep duration.
- Apply a log10 transformation to mass to make relationships more linear.
- Fit separate linear models for each diet category (carnivores, omnivores, herbivores).
- Visualize the data points and fitted lines on a combined plot and discuss findings.

Contents
--------
- `animal_sleep.ipynb` — Jupyter notebook with the analysis, plots, and modeling steps.
- `animal-sleep.csv` — Dataset used in the notebook (77 species; columns include `animal`, `diet`, `sleep`, and `mass`).
- `linear_model.py` — Small helper class used by the notebook to fit, predict, and plot linear models.

Quick links
-----------
- Open the notebook in Google Colab: https://colab.research.google.com/github/mutambo/animal-sleep/blob/main/animal_sleep.ipynb

Data schema
-----------
Expected columns in `animal-sleep.csv`:
- `animal` — species name (string)
- `diet` — one of `carnivore`, `omnivore`, or `herbivore` (string)
- `sleep` — average hours of sleep per day (float)
- `mass` — average body mass in kilograms (float)

Getting started (local)
-----------------------
1. Clone the repository:
   git clone https://github.com/mutambo/animal-sleep.git
   cd animal-sleep

2. (Optional) Create and activate a virtual environment:
   python -m venv venv
   source venv/bin/activate  # macOS / Linux
   venv\Scripts\activate     # Windows

3. Install dependencies:
   pip install pandas matplotlib jupyter

   If `linear_model.py` depends on other packages, install them as needed.

4. Start Jupyter and open the notebook:
   jupyter notebook animal_sleep.ipynb

Running in Google Colab
-----------------------
- The notebook includes a Colab badge and instructions to upload `animal-sleep.csv` and `linear_model.py` when using Colab. You can open the notebook directly using the Colab link in Quick links above.

What the notebook does
----------------------
- Loads `animal-sleep.csv` into a pandas DataFrame and prints a sample.
- Visualizes mass vs sleep and log10(mass) vs sleep.
- Adds a `log10_mass` column (log10 transformation of `mass`) for modeling.
- Splits the data into three subsets by `diet` (carnivore, omnivore, herbivore).
- Uses `LinearModel` (from `linear_model.py`) to fit separate linear regressions for each subset, plot best-fit lines, and print model summaries.

LinearModel API (used in the notebook)
-------------------------------------
The notebook demonstrates using `LinearModel` with a simple API similar to:

- linear = LinearModel()
- linear.fit(x, y)
- linear.predict(x)
- linear.plot_model(x_min, x_max, color="black")
- linear.print_model_info()

(See `linear_model.py` for the actual implementation and details.)

Project ideas / next steps
--------------------------
- Add cross-validation or confidence intervals for the fitted lines.
- Try polynomial or robust regression to handle potential outliers.
- Explore additional covariates (e.g., sleep type, nocturnal/diurnal, phylogenetic corrections).
- Publish results and visualizations in a short write-up or blog post.

Contributing
------------
Contributions and improvements are welcome. If you add features, please:
- Keep the notebook reproducible (document additional dependencies).
- Add tests for helper modules if you introduce non-trivial logic.
- Consider adding a `requirements.txt` or `environment.yml` for reproducibility.
