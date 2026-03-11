Extra OPTICS Models
===================

A repository for all the extra models that aren't part of the official VPOD releases.

Overview
--------

The core OPTICS installation includes standard, generalized models (`whole-dataset`, `whole-dataset-mnm`, `wildtype`, `wildtype-mnm`, and `type-one`) out of the box. To keep the base installation lightweight and manageable, we provide specialized and subset models here as "extra models".

If you try to run OPTICS predictions or SHAP explanations with an extra model that isn't installed, the script will automatically pause and direct you to this repository.

### Available Extra Models

-   `vertebrate` & `vertebrate-mnm`

-   `invertebrate` & `invertebrate-mnm`

-   `wildtype-vert` & `wildtype-vert-mnm`

-   `wildtype-mut`

Installation & Usage
--------------------

To use any of these models in your OPTICS scripts, you must manually download them and place them into your local OPTICS directory structure.

1.  **Download the Required Files** Locate the specific model `.pkl` file (or bootstrap folder) you need from this repository. Ensure you select the correct VPOD version (e.g., `vpod_1.3`) and encoding method (`aa_prop` or `one_hot`) that you intend to use.

> **📥 You can also bulk-download zipp-folders with _box_**: Visit our box-hub, [here](https://ucsb.box.com/v/extra-optics-models), and download the zipped folders containing the regular 'single' models or bootstrap ensemble folders.  

2.  **Move Files to Your Local Installation** Transfer the downloaded files into your local OPTICS `models` directory:

    -   **For standard (single) regression models:** Place the `.pkl` file into the corresponding regression model path

        `models/reg_models/<version>/<encoding>/`

    -   **For bootstrap model ensembles:** Place the entire folder into the bootstrap path (**Make sure to download the corresponding standard regression model as well!**)

        `models/bs_models/<version>/<encoding>/`

3.  **Run Your Command Line Scripts** Once the files are correctly placed, you can run your `optics_predictions.py` or `optics_shap.py` script exactly as you normally would, using the `-m` flag to specify your newly added model (e.g., `-m vertebrate`).

4.  **Enable Models in the GUI (`run_optics_gui.py`)** To prevent errors, extra models are hidden from the GUI dropdown menu by default. Once you have downloaded and installed an extra model, you must manually add it to the GUI's selection list to use it:

    -   Open `run_optics_gui.py` in any text editor.

    -   Locate the `OpticsGUIFrame` class setup (around line 155).

    -   Find the `self.model_choices` list.

    -   Add your newly downloaded model name to the active list, OR comment out the restricted list and uncomment the full list of models provided directly below it.
  
