# GDC-tricks

## The GDC data portal
You can access the GDC data portal at https://gdc-portal.nci.nih.gov/

### Finding a dataset 
- Click on the "data" tab
![data tab](GDC-data.png?raw=true "Data tab")
- Choose the appropriate criteria (tissue, cancer type, data type, etc)
- Click on the "files" tab
![files tab](GDC-files.png?raw=true "files tab")
- Click on the cart icon to select files
![cart](GDC-cart.png?raw=true "cart")

### Downloading data
- Click on the "cart" tab
![cart tab](GDC-cart_tab.png?raw=true "cart tab")
- Click on the "Download" button, and then on "Manifest"; save it to the appropriate directory
![manifest](GDC-manifest.png?raw=true "manifest")
- Download the GDC client at https://gdc.cancer.gov/access-data/gdc-data-transfer-tool
- Launch the GDC client using the -m option to specify the path to the Manifest file:
```bash
gdc-client download -m gdc_manifest.txt
```
If the data mentionned in the manifest file is access-restricted, you further need to download a token file that identifies you. To do so, click on your user name in the top right of the page, and select "Download token"; save it to the appropriate directory. 
![token](GDC-token.png?raw=true "user token")

You can then llaunch the GDC client using both -m (manifest) and -t (token) options:
```bash
gdc-client download -m gdc_manifest.txt  -t gdc-user-token.txt
```

You can also compile the gdc-client yourself using the sources from https://github.com/NCI-GDC/gdc-client. To do so, you can clone the git repository:
```bash
git clone https://github.com/NCI-GDC/gdc-client
```
Then compile the sources using python package setuptools:
```bash
python setup.py build
python setup.py install
```
