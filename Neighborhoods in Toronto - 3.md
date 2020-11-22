```python
!pip install beautifulsoup4
!pip install lxml
import requests # library to handle requests
import pandas as pd # library for data analsysis
import numpy as np # library to handle data in a vectorized manner
import random # library for random number generation

!conda install -c conda-forge geopy --yes 
from geopy.geocoders import Nominatim # module to convert an address into latitude and longitude values

# libraries for displaying images
from IPython.display import Image 
from IPython.core.display import HTML 


from IPython.display import display_html
import pandas as pd
import numpy as np
    
# tranforming json file into a pandas dataframe library
from pandas.io.json import json_normalize

!conda install -c conda-forge folium=0.5.0 --yes
import folium # plotting library
from bs4 import BeautifulSoup
from sklearn.cluster import KMeans
import matplotlib.cm as cm
import matplotlib.colors as colors

print('Folium installed')
print('Libraries imported.')
```

    Collecting beautifulsoup4
    [?25l  Downloading https://files.pythonhosted.org/packages/d1/41/e6495bd7d3781cee623ce23ea6ac73282a373088fcd0ddc809a047b18eae/beautifulsoup4-4.9.3-py3-none-any.whl (115kB)
    [K     |████████████████████████████████| 122kB 4.9MB/s eta 0:00:01
    [?25hCollecting soupsieve>1.2; python_version >= "3.0" (from beautifulsoup4)
      Downloading https://files.pythonhosted.org/packages/6f/8f/457f4a5390eeae1cc3aeab89deb7724c965be841ffca6cfca9197482e470/soupsieve-2.0.1-py3-none-any.whl
    Installing collected packages: soupsieve, beautifulsoup4
    Successfully installed beautifulsoup4-4.9.3 soupsieve-2.0.1
    Collecting lxml
    [?25l  Downloading https://files.pythonhosted.org/packages/64/28/0b761b64ecbd63d272ed0e7a6ae6e4402fc37886b59181bfdf274424d693/lxml-4.6.1-cp36-cp36m-manylinux1_x86_64.whl (5.5MB)
    [K     |████████████████████████████████| 5.5MB 7.4MB/s eta 0:00:01
    [?25hInstalling collected packages: lxml
    Successfully installed lxml-4.6.1
    Collecting package metadata (current_repodata.json): done
    Solving environment: done
    
    
    ==> WARNING: A newer version of conda exists. <==
      current version: 4.9.1
      latest version: 4.9.2
    
    Please update conda by running
    
        $ conda update -n base -c defaults conda
    
    
    
    ## Package Plan ##
    
      environment location: /home/jupyterlab/conda/envs/python
    
      added / updated specs:
        - geopy
    
    
    The following packages will be downloaded:
    
        package                    |            build
        ---------------------------|-----------------
        ca-certificates-2020.11.8  |       ha878542_0         145 KB  conda-forge
        certifi-2020.11.8          |   py36h5fab9bb_0         150 KB  conda-forge
        geographiclib-1.50         |             py_0          34 KB  conda-forge
        geopy-2.0.0                |     pyh9f0ad1d_0          63 KB  conda-forge
        ------------------------------------------------------------
                                               Total:         392 KB
    
    The following NEW packages will be INSTALLED:
    
      geographiclib      conda-forge/noarch::geographiclib-1.50-py_0
      geopy              conda-forge/noarch::geopy-2.0.0-pyh9f0ad1d_0
    
    The following packages will be UPDATED:
    
      ca-certificates                      2020.6.20-hecda079_0 --> 2020.11.8-ha878542_0
      certifi                          2020.6.20-py36h9880bd3_2 --> 2020.11.8-py36h5fab9bb_0
    
    
    
    Downloading and Extracting Packages
    certifi-2020.11.8    | 150 KB    | ##################################### | 100% 
    ca-certificates-2020 | 145 KB    | ##################################### | 100% 
    geopy-2.0.0          | 63 KB     | ##################################### | 100% 
    geographiclib-1.50   | 34 KB     | ##################################### | 100% 
    Preparing transaction: done
    Verifying transaction: done
    Executing transaction: done
    Collecting package metadata (current_repodata.json): done
    Solving environment: failed with initial frozen solve. Retrying with flexible solve.
    Collecting package metadata (repodata.json): done
    Solving environment: done
    
    
    ==> WARNING: A newer version of conda exists. <==
      current version: 4.9.1
      latest version: 4.9.2
    
    Please update conda by running
    
        $ conda update -n base -c defaults conda
    
    
    
    ## Package Plan ##
    
      environment location: /home/jupyterlab/conda/envs/python
    
      added / updated specs:
        - folium=0.5.0
    
    
    The following packages will be downloaded:
    
        package                    |            build
        ---------------------------|-----------------
        altair-4.1.0               |             py_1         614 KB  conda-forge
        attrs-20.3.0               |     pyhd3deb0d_0          41 KB  conda-forge
        branca-0.4.1               |             py_0          26 KB  conda-forge
        brotlipy-0.7.0             |py36he6145b8_1001         347 KB  conda-forge
        chardet-3.0.4              |py36h9880bd3_1008         194 KB  conda-forge
        cryptography-3.2.1         |   py36h6ec43e4_0         633 KB  conda-forge
        entrypoints-0.3            |  pyhd8ed1ab_1003           8 KB  conda-forge
        folium-0.5.0               |             py_0          45 KB  conda-forge
        pandas-1.1.4               |   py36hd87012b_0        10.5 MB  conda-forge
        pyrsistent-0.17.3          |   py36h1d69622_1          89 KB  conda-forge
        pysocks-1.7.1              |   py36h9880bd3_2          27 KB  conda-forge
        pytz-2020.4                |     pyhd8ed1ab_0         229 KB  conda-forge
        requests-2.25.0            |     pyhd3deb0d_0          51 KB  conda-forge
        toolz-0.11.1               |             py_0          46 KB  conda-forge
        vincent-0.4.4              |             py_1          28 KB  conda-forge
        ------------------------------------------------------------
                                               Total:        12.8 MB
    
    The following NEW packages will be INSTALLED:
    
      altair             conda-forge/noarch::altair-4.1.0-py_1
      attrs              conda-forge/noarch::attrs-20.3.0-pyhd3deb0d_0
      branca             conda-forge/noarch::branca-0.4.1-py_0
      brotlipy           conda-forge/linux-64::brotlipy-0.7.0-py36he6145b8_1001
      chardet            conda-forge/linux-64::chardet-3.0.4-py36h9880bd3_1008
      cryptography       conda-forge/linux-64::cryptography-3.2.1-py36h6ec43e4_0
      entrypoints        conda-forge/noarch::entrypoints-0.3-pyhd8ed1ab_1003
      folium             conda-forge/noarch::folium-0.5.0-py_0
      idna               conda-forge/noarch::idna-2.10-pyh9f0ad1d_0
      importlib_metadata conda-forge/noarch::importlib_metadata-2.0.0-1
      jinja2             conda-forge/noarch::jinja2-2.11.2-pyh9f0ad1d_0
      jsonschema         conda-forge/noarch::jsonschema-3.2.0-py_2
      markupsafe         conda-forge/linux-64::markupsafe-1.1.1-py36he6145b8_2
      pandas             conda-forge/linux-64::pandas-1.1.4-py36hd87012b_0
      pyopenssl          conda-forge/noarch::pyopenssl-19.1.0-py_1
      pyrsistent         conda-forge/linux-64::pyrsistent-0.17.3-py36h1d69622_1
      pysocks            conda-forge/linux-64::pysocks-1.7.1-py36h9880bd3_2
      pytz               conda-forge/noarch::pytz-2020.4-pyhd8ed1ab_0
      requests           conda-forge/noarch::requests-2.25.0-pyhd3deb0d_0
      toolz              conda-forge/noarch::toolz-0.11.1-py_0
      urllib3            conda-forge/noarch::urllib3-1.25.11-py_0
      vincent            conda-forge/noarch::vincent-0.4.4-py_1
    
    
    
    Downloading and Extracting Packages
    entrypoints-0.3      | 8 KB      | ##################################### | 100% 
    attrs-20.3.0         | 41 KB     | ##################################### | 100% 
    pyrsistent-0.17.3    | 89 KB     | ##################################### | 100% 
    pytz-2020.4          | 229 KB    | ##################################### | 100% 
    cryptography-3.2.1   | 633 KB    | ##################################### | 100% 
    folium-0.5.0         | 45 KB     | ##################################### | 100% 
    pandas-1.1.4         | 10.5 MB   | ##################################### | 100% 
    pysocks-1.7.1        | 27 KB     | ##################################### | 100% 
    brotlipy-0.7.0       | 347 KB    | ##################################### | 100% 
    chardet-3.0.4        | 194 KB    | ##################################### | 100% 
    branca-0.4.1         | 26 KB     | ##################################### | 100% 
    requests-2.25.0      | 51 KB     | ##################################### | 100% 
    altair-4.1.0         | 614 KB    | ##################################### | 100% 
    toolz-0.11.1         | 46 KB     | ##################################### | 100% 
    vincent-0.4.4        | 28 KB     | ##################################### | 100% 
    Preparing transaction: done
    Verifying transaction: done
    Executing transaction: done
    Folium installed
    Libraries imported.



```python
source = requests.get('https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M').text
soup=BeautifulSoup(source,'lxml')
print(soup.title)
from IPython.display import display_html
tab = str(soup.table)
display_html(tab,raw=True)
```

    <title>List of postal codes of Canada: M - Wikipedia</title>



<table class="wikitable sortable">
<tbody><tr>
<th>Postal Code
</th>
<th>Borough
</th>
<th>Neighbourhood
</th></tr>
<tr>
<td>M1A
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M2A
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M3A
</td>
<td>North York
</td>
<td>Parkwoods
</td></tr>
<tr>
<td>M4A
</td>
<td>North York
</td>
<td>Victoria Village
</td></tr>
<tr>
<td>M5A
</td>
<td>Downtown Toronto
</td>
<td>Regent Park, Harbourfront
</td></tr>
<tr>
<td>M6A
</td>
<td>North York
</td>
<td>Lawrence Manor, Lawrence Heights
</td></tr>
<tr>
<td>M7A
</td>
<td>Downtown Toronto
</td>
<td>Queen's Park, Ontario Provincial Government
</td></tr>
<tr>
<td>M8A
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9A
</td>
<td>Etobicoke
</td>
<td>Islington Avenue, Humber Valley Village
</td></tr>
<tr>
<td>M1B
</td>
<td>Scarborough
</td>
<td>Malvern, Rouge
</td></tr>
<tr>
<td>M2B
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M3B
</td>
<td>North York
</td>
<td>Don Mills
</td></tr>
<tr>
<td>M4B
</td>
<td>East York
</td>
<td>Parkview Hill, Woodbine Gardens
</td></tr>
<tr>
<td>M5B
</td>
<td>Downtown Toronto
</td>
<td>Garden District, Ryerson
</td></tr>
<tr>
<td>M6B
</td>
<td>North York
</td>
<td>Glencairn
</td></tr>
<tr>
<td>M7B
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8B
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9B
</td>
<td>Etobicoke
</td>
<td>West Deane Park, Princess Gardens, Martin Grove, Islington, Cloverdale
</td></tr>
<tr>
<td>M1C
</td>
<td>Scarborough
</td>
<td>Rouge Hill, Port Union, Highland Creek
</td></tr>
<tr>
<td>M2C
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M3C
</td>
<td>North York
</td>
<td>Don Mills
</td></tr>
<tr>
<td>M4C
</td>
<td>East York
</td>
<td>Woodbine Heights
</td></tr>
<tr>
<td>M5C
</td>
<td>Downtown Toronto
</td>
<td>St. James Town
</td></tr>
<tr>
<td>M6C
</td>
<td>York
</td>
<td>Humewood-Cedarvale
</td></tr>
<tr>
<td>M7C
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8C
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9C
</td>
<td>Etobicoke
</td>
<td>Eringate, Bloordale Gardens, Old Burnhamthorpe, Markland Wood
</td></tr>
<tr>
<td>M1E
</td>
<td>Scarborough
</td>
<td>Guildwood, Morningside, West Hill
</td></tr>
<tr>
<td>M2E
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M3E
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M4E
</td>
<td>East Toronto
</td>
<td>The Beaches
</td></tr>
<tr>
<td>M5E
</td>
<td>Downtown Toronto
</td>
<td>Berczy Park
</td></tr>
<tr>
<td>M6E
</td>
<td>York
</td>
<td>Caledonia-Fairbanks
</td></tr>
<tr>
<td>M7E
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8E
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9E
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M1G
</td>
<td>Scarborough
</td>
<td>Woburn
</td></tr>
<tr>
<td>M2G
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M3G
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M4G
</td>
<td>East York
</td>
<td>Leaside
</td></tr>
<tr>
<td>M5G
</td>
<td>Downtown Toronto
</td>
<td>Central Bay Street
</td></tr>
<tr>
<td>M6G
</td>
<td>Downtown Toronto
</td>
<td>Christie
</td></tr>
<tr>
<td>M7G
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8G
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9G
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M1H
</td>
<td>Scarborough
</td>
<td>Cedarbrae
</td></tr>
<tr>
<td>M2H
</td>
<td>North York
</td>
<td>Hillcrest Village
</td></tr>
<tr>
<td>M3H
</td>
<td>North York
</td>
<td>Bathurst Manor, Wilson Heights, Downsview North
</td></tr>
<tr>
<td>M4H
</td>
<td>East York
</td>
<td>Thorncliffe Park
</td></tr>
<tr>
<td>M5H
</td>
<td>Downtown Toronto
</td>
<td>Richmond, Adelaide, King
</td></tr>
<tr>
<td>M6H
</td>
<td>West Toronto
</td>
<td>Dufferin, Dovercourt Village
</td></tr>
<tr>
<td>M7H
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8H
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9H
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M1J
</td>
<td>Scarborough
</td>
<td>Scarborough Village
</td></tr>
<tr>
<td>M2J
</td>
<td>North York
</td>
<td>Fairview, Henry Farm, Oriole
</td></tr>
<tr>
<td>M3J
</td>
<td>North York
</td>
<td>Northwood Park, York University
</td></tr>
<tr>
<td>M4J
</td>
<td>East York
</td>
<td>East Toronto, Broadview North (Old East York)
</td></tr>
<tr>
<td>M5J
</td>
<td>Downtown Toronto
</td>
<td>Harbourfront East, Union Station, Toronto Islands
</td></tr>
<tr>
<td>M6J
</td>
<td>West Toronto
</td>
<td>Little Portugal, Trinity
</td></tr>
<tr>
<td>M7J
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8J
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9J
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M1K
</td>
<td>Scarborough
</td>
<td>Kennedy Park, Ionview, East Birchmount Park
</td></tr>
<tr>
<td>M2K
</td>
<td>North York
</td>
<td>Bayview Village
</td></tr>
<tr>
<td>M3K
</td>
<td>North York
</td>
<td>Downsview
</td></tr>
<tr>
<td>M4K
</td>
<td>East Toronto
</td>
<td>The Danforth West, Riverdale
</td></tr>
<tr>
<td>M5K
</td>
<td>Downtown Toronto
</td>
<td>Toronto Dominion Centre, Design Exchange
</td></tr>
<tr>
<td>M6K
</td>
<td>West Toronto
</td>
<td>Brockton, Parkdale Village, Exhibition Place
</td></tr>
<tr>
<td>M7K
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8K
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9K
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M1L
</td>
<td>Scarborough
</td>
<td>Golden Mile, Clairlea, Oakridge
</td></tr>
<tr>
<td>M2L
</td>
<td>North York
</td>
<td>York Mills, Silver Hills
</td></tr>
<tr>
<td>M3L
</td>
<td>North York
</td>
<td>Downsview
</td></tr>
<tr>
<td>M4L
</td>
<td>East Toronto
</td>
<td>India Bazaar, The Beaches West
</td></tr>
<tr>
<td>M5L
</td>
<td>Downtown Toronto
</td>
<td>Commerce Court, Victoria Hotel
</td></tr>
<tr>
<td>M6L
</td>
<td>North York
</td>
<td>North Park, Maple Leaf Park, Upwood Park
</td></tr>
<tr>
<td>M7L
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8L
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9L
</td>
<td>North York
</td>
<td>Humber Summit
</td></tr>
<tr>
<td>M1M
</td>
<td>Scarborough
</td>
<td>Cliffside, Cliffcrest, Scarborough Village West
</td></tr>
<tr>
<td>M2M
</td>
<td>North York
</td>
<td>Willowdale, Newtonbrook
</td></tr>
<tr>
<td>M3M
</td>
<td>North York
</td>
<td>Downsview
</td></tr>
<tr>
<td>M4M
</td>
<td>East Toronto
</td>
<td>Studio District
</td></tr>
<tr>
<td>M5M
</td>
<td>North York
</td>
<td>Bedford Park, Lawrence Manor East
</td></tr>
<tr>
<td>M6M
</td>
<td>York
</td>
<td>Del Ray, Mount Dennis, Keelsdale and Silverthorn
</td></tr>
<tr>
<td>M7M
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8M
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9M
</td>
<td>North York
</td>
<td>Humberlea, Emery
</td></tr>
<tr>
<td>M1N
</td>
<td>Scarborough
</td>
<td>Birch Cliff, Cliffside West
</td></tr>
<tr>
<td>M2N
</td>
<td>North York
</td>
<td>Willowdale, Willowdale East
</td></tr>
<tr>
<td>M3N
</td>
<td>North York
</td>
<td>Downsview
</td></tr>
<tr>
<td>M4N
</td>
<td>Central Toronto
</td>
<td>Lawrence Park
</td></tr>
<tr>
<td>M5N
</td>
<td>Central Toronto
</td>
<td>Roselawn
</td></tr>
<tr>
<td>M6N
</td>
<td>York
</td>
<td>Runnymede, The Junction North
</td></tr>
<tr>
<td>M7N
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8N
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9N
</td>
<td>York
</td>
<td>Weston
</td></tr>
<tr>
<td>M1P
</td>
<td>Scarborough
</td>
<td>Dorset Park, Wexford Heights, Scarborough Town Centre
</td></tr>
<tr>
<td>M2P
</td>
<td>North York
</td>
<td>York Mills West
</td></tr>
<tr>
<td>M3P
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M4P
</td>
<td>Central Toronto
</td>
<td>Davisville North
</td></tr>
<tr>
<td>M5P
</td>
<td>Central Toronto
</td>
<td>Forest Hill North &amp; West, Forest Hill Road Park
</td></tr>
<tr>
<td>M6P
</td>
<td>West Toronto
</td>
<td>High Park, The Junction South
</td></tr>
<tr>
<td>M7P
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8P
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9P
</td>
<td>Etobicoke
</td>
<td>Westmount
</td></tr>
<tr>
<td>M1R
</td>
<td>Scarborough
</td>
<td>Wexford, Maryvale
</td></tr>
<tr>
<td>M2R
</td>
<td>North York
</td>
<td>Willowdale, Willowdale West
</td></tr>
<tr>
<td>M3R
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M4R
</td>
<td>Central Toronto
</td>
<td>North Toronto West,  Lawrence Park
</td></tr>
<tr>
<td>M5R
</td>
<td>Central Toronto
</td>
<td>The Annex, North Midtown, Yorkville
</td></tr>
<tr>
<td>M6R
</td>
<td>West Toronto
</td>
<td>Parkdale, Roncesvalles
</td></tr>
<tr>
<td>M7R
</td>
<td>Mississauga
</td>
<td>Canada Post Gateway Processing Centre
</td></tr>
<tr>
<td>M8R
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9R
</td>
<td>Etobicoke
</td>
<td>Kingsview Village, St. Phillips, Martin Grove Gardens, Richview Gardens
</td></tr>
<tr>
<td>M1S
</td>
<td>Scarborough
</td>
<td>Agincourt
</td></tr>
<tr>
<td>M2S
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M3S
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M4S
</td>
<td>Central Toronto
</td>
<td>Davisville
</td></tr>
<tr>
<td>M5S
</td>
<td>Downtown Toronto
</td>
<td>University of Toronto, Harbord
</td></tr>
<tr>
<td>M6S
</td>
<td>West Toronto
</td>
<td>Runnymede, Swansea
</td></tr>
<tr>
<td>M7S
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8S
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9S
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M1T
</td>
<td>Scarborough
</td>
<td>Clarks Corners, Tam O'Shanter, Sullivan
</td></tr>
<tr>
<td>M2T
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M3T
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M4T
</td>
<td>Central Toronto
</td>
<td>Moore Park, Summerhill East
</td></tr>
<tr>
<td>M5T
</td>
<td>Downtown Toronto
</td>
<td>Kensington Market, Chinatown, Grange Park
</td></tr>
<tr>
<td>M6T
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M7T
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8T
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M9T
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M1V
</td>
<td>Scarborough
</td>
<td>Milliken, Agincourt North, Steeles East, L'Amoreaux East
</td></tr>
<tr>
<td>M2V
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M3V
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M4V
</td>
<td>Central Toronto
</td>
<td>Summerhill West, Rathnelly, South Hill, Forest Hill SE, Deer Park
</td></tr>
<tr>
<td>M5V
</td>
<td>Downtown Toronto
</td>
<td>CN Tower, King and Spadina, Railway Lands, Harbourfront West, Bathurst Quay, South Niagara, Island airport
</td></tr>
<tr>
<td>M6V
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M7V
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8V
</td>
<td>Etobicoke
</td>
<td>New Toronto, Mimico South, Humber Bay Shores
</td></tr>
<tr>
<td>M9V
</td>
<td>Etobicoke
</td>
<td>South Steeles, Silverstone, Humbergate, Jamestown, Mount Olive, Beaumond Heights, Thistletown, Albion Gardens
</td></tr>
<tr>
<td>M1W
</td>
<td>Scarborough
</td>
<td>Steeles West, L'Amoreaux West
</td></tr>
<tr>
<td>M2W
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M3W
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M4W
</td>
<td>Downtown Toronto
</td>
<td>Rosedale
</td></tr>
<tr>
<td>M5W
</td>
<td>Downtown Toronto
</td>
<td>Stn A PO Boxes
</td></tr>
<tr>
<td>M6W
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M7W
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8W
</td>
<td>Etobicoke
</td>
<td>Alderwood, Long Branch
</td></tr>
<tr>
<td>M9W
</td>
<td>Etobicoke
</td>
<td>Northwest, West Humber - Clairville
</td></tr>
<tr>
<td>M1X
</td>
<td>Scarborough
</td>
<td>Upper Rouge
</td></tr>
<tr>
<td>M2X
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M3X
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M4X
</td>
<td>Downtown Toronto
</td>
<td>St. James Town, Cabbagetown
</td></tr>
<tr>
<td>M5X
</td>
<td>Downtown Toronto
</td>
<td>First Canadian Place, Underground city
</td></tr>
<tr>
<td>M6X
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M7X
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8X
</td>
<td>Etobicoke
</td>
<td>The Kingsway, Montgomery Road, Old Mill North
</td></tr>
<tr>
<td>M9X
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M1Y
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M2Y
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M3Y
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M4Y
</td>
<td>Downtown Toronto
</td>
<td>Church and Wellesley
</td></tr>
<tr>
<td>M5Y
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M6Y
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M7Y
</td>
<td>East Toronto
</td>
<td>Business reply mail Processing Centre, South Central Letter Processing Plant Toronto
</td></tr>
<tr>
<td>M8Y
</td>
<td>Etobicoke
</td>
<td>Old Mill South, King's Mill Park, Sunnylea, Humber Bay, Mimico NE, The Queensway East, Royal York South East, Kingsway Park South East
</td></tr>
<tr>
<td>M9Y
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M1Z
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M2Z
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M3Z
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M4Z
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M5Z
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M6Z
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M7Z
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr>
<tr>
<td>M8Z
</td>
<td>Etobicoke
</td>
<td>Mimico NW, The Queensway West, South of Bloor, Kingsway Park South West, Royal York South West
</td></tr>
<tr>
<td>M9Z
</td>
<td>Not assigned
</td>
<td>Not assigned
</td></tr></tbody></table>



```python
dfs = pd.read_html(tab)
df=dfs[0]
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Postal Code</th>
      <th>Borough</th>
      <th>Neighbourhood</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>M1A</td>
      <td>Not assigned</td>
      <td>Not assigned</td>
    </tr>
    <tr>
      <th>1</th>
      <td>M2A</td>
      <td>Not assigned</td>
      <td>Not assigned</td>
    </tr>
    <tr>
      <th>2</th>
      <td>M3A</td>
      <td>North York</td>
      <td>Parkwoods</td>
    </tr>
    <tr>
      <th>3</th>
      <td>M4A</td>
      <td>North York</td>
      <td>Victoria Village</td>
    </tr>
    <tr>
      <th>4</th>
      <td>M5A</td>
      <td>Downtown Toronto</td>
      <td>Regent Park, Harbourfront</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1 = df[df.Borough != 'Not assigned']
```


```python
df2 = df1.groupby(['Postal Code','Borough'], sort=False).agg(', '.join)
df2.reset_index(inplace=True)
```


```python
df2['Neighbourhood'] = np.where(df2['Neighbourhood'] == 'Not assigned',df2['Borough'], df2['Neighbourhood'])

df2
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Postal Code</th>
      <th>Borough</th>
      <th>Neighbourhood</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>M3A</td>
      <td>North York</td>
      <td>Parkwoods</td>
    </tr>
    <tr>
      <th>1</th>
      <td>M4A</td>
      <td>North York</td>
      <td>Victoria Village</td>
    </tr>
    <tr>
      <th>2</th>
      <td>M5A</td>
      <td>Downtown Toronto</td>
      <td>Regent Park, Harbourfront</td>
    </tr>
    <tr>
      <th>3</th>
      <td>M6A</td>
      <td>North York</td>
      <td>Lawrence Manor, Lawrence Heights</td>
    </tr>
    <tr>
      <th>4</th>
      <td>M7A</td>
      <td>Downtown Toronto</td>
      <td>Queen's Park, Ontario Provincial Government</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>98</th>
      <td>M8X</td>
      <td>Etobicoke</td>
      <td>The Kingsway, Montgomery Road, Old Mill North</td>
    </tr>
    <tr>
      <th>99</th>
      <td>M4Y</td>
      <td>Downtown Toronto</td>
      <td>Church and Wellesley</td>
    </tr>
    <tr>
      <th>100</th>
      <td>M7Y</td>
      <td>East Toronto</td>
      <td>Business reply mail Processing Centre, South C...</td>
    </tr>
    <tr>
      <th>101</th>
      <td>M8Y</td>
      <td>Etobicoke</td>
      <td>Old Mill South, King's Mill Park, Sunnylea, Hu...</td>
    </tr>
    <tr>
      <th>102</th>
      <td>M8Z</td>
      <td>Etobicoke</td>
      <td>Mimico NW, The Queensway West, South of Bloor,...</td>
    </tr>
  </tbody>
</table>
<p>103 rows × 3 columns</p>
</div>




```python
lat_lon = pd.read_csv('https://cocl.us/Geospatial_data')
lat_lon.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Postal Code</th>
      <th>Latitude</th>
      <th>Longitude</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>M1B</td>
      <td>43.806686</td>
      <td>-79.194353</td>
    </tr>
    <tr>
      <th>1</th>
      <td>M1C</td>
      <td>43.784535</td>
      <td>-79.160497</td>
    </tr>
    <tr>
      <th>2</th>
      <td>M1E</td>
      <td>43.763573</td>
      <td>-79.188711</td>
    </tr>
    <tr>
      <th>3</th>
      <td>M1G</td>
      <td>43.770992</td>
      <td>-79.216917</td>
    </tr>
    <tr>
      <th>4</th>
      <td>M1H</td>
      <td>43.773136</td>
      <td>-79.239476</td>
    </tr>
  </tbody>
</table>
</div>




```python
df3 = pd.merge(df2,lat_lon,on='Postal Code')
df3.head()

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Postal Code</th>
      <th>Borough</th>
      <th>Neighbourhood</th>
      <th>Latitude</th>
      <th>Longitude</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>M3A</td>
      <td>North York</td>
      <td>Parkwoods</td>
      <td>43.753259</td>
      <td>-79.329656</td>
    </tr>
    <tr>
      <th>1</th>
      <td>M4A</td>
      <td>North York</td>
      <td>Victoria Village</td>
      <td>43.725882</td>
      <td>-79.315572</td>
    </tr>
    <tr>
      <th>2</th>
      <td>M5A</td>
      <td>Downtown Toronto</td>
      <td>Regent Park, Harbourfront</td>
      <td>43.654260</td>
      <td>-79.360636</td>
    </tr>
    <tr>
      <th>3</th>
      <td>M6A</td>
      <td>North York</td>
      <td>Lawrence Manor, Lawrence Heights</td>
      <td>43.718518</td>
      <td>-79.464763</td>
    </tr>
    <tr>
      <th>4</th>
      <td>M7A</td>
      <td>Downtown Toronto</td>
      <td>Queen's Park, Ontario Provincial Government</td>
      <td>43.662301</td>
      <td>-79.389494</td>
    </tr>
  </tbody>
</table>
</div>




```python
df4 = df3[df3['Borough'].str.contains('Toronto',regex=False)]
df4
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Postal Code</th>
      <th>Borough</th>
      <th>Neighbourhood</th>
      <th>Latitude</th>
      <th>Longitude</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>M5A</td>
      <td>Downtown Toronto</td>
      <td>Regent Park, Harbourfront</td>
      <td>43.654260</td>
      <td>-79.360636</td>
    </tr>
    <tr>
      <th>4</th>
      <td>M7A</td>
      <td>Downtown Toronto</td>
      <td>Queen's Park, Ontario Provincial Government</td>
      <td>43.662301</td>
      <td>-79.389494</td>
    </tr>
    <tr>
      <th>9</th>
      <td>M5B</td>
      <td>Downtown Toronto</td>
      <td>Garden District, Ryerson</td>
      <td>43.657162</td>
      <td>-79.378937</td>
    </tr>
    <tr>
      <th>15</th>
      <td>M5C</td>
      <td>Downtown Toronto</td>
      <td>St. James Town</td>
      <td>43.651494</td>
      <td>-79.375418</td>
    </tr>
    <tr>
      <th>19</th>
      <td>M4E</td>
      <td>East Toronto</td>
      <td>The Beaches</td>
      <td>43.676357</td>
      <td>-79.293031</td>
    </tr>
    <tr>
      <th>20</th>
      <td>M5E</td>
      <td>Downtown Toronto</td>
      <td>Berczy Park</td>
      <td>43.644771</td>
      <td>-79.373306</td>
    </tr>
    <tr>
      <th>24</th>
      <td>M5G</td>
      <td>Downtown Toronto</td>
      <td>Central Bay Street</td>
      <td>43.657952</td>
      <td>-79.387383</td>
    </tr>
    <tr>
      <th>25</th>
      <td>M6G</td>
      <td>Downtown Toronto</td>
      <td>Christie</td>
      <td>43.669542</td>
      <td>-79.422564</td>
    </tr>
    <tr>
      <th>30</th>
      <td>M5H</td>
      <td>Downtown Toronto</td>
      <td>Richmond, Adelaide, King</td>
      <td>43.650571</td>
      <td>-79.384568</td>
    </tr>
    <tr>
      <th>31</th>
      <td>M6H</td>
      <td>West Toronto</td>
      <td>Dufferin, Dovercourt Village</td>
      <td>43.669005</td>
      <td>-79.442259</td>
    </tr>
    <tr>
      <th>36</th>
      <td>M5J</td>
      <td>Downtown Toronto</td>
      <td>Harbourfront East, Union Station, Toronto Islands</td>
      <td>43.640816</td>
      <td>-79.381752</td>
    </tr>
    <tr>
      <th>37</th>
      <td>M6J</td>
      <td>West Toronto</td>
      <td>Little Portugal, Trinity</td>
      <td>43.647927</td>
      <td>-79.419750</td>
    </tr>
    <tr>
      <th>41</th>
      <td>M4K</td>
      <td>East Toronto</td>
      <td>The Danforth West, Riverdale</td>
      <td>43.679557</td>
      <td>-79.352188</td>
    </tr>
    <tr>
      <th>42</th>
      <td>M5K</td>
      <td>Downtown Toronto</td>
      <td>Toronto Dominion Centre, Design Exchange</td>
      <td>43.647177</td>
      <td>-79.381576</td>
    </tr>
    <tr>
      <th>43</th>
      <td>M6K</td>
      <td>West Toronto</td>
      <td>Brockton, Parkdale Village, Exhibition Place</td>
      <td>43.636847</td>
      <td>-79.428191</td>
    </tr>
    <tr>
      <th>47</th>
      <td>M4L</td>
      <td>East Toronto</td>
      <td>India Bazaar, The Beaches West</td>
      <td>43.668999</td>
      <td>-79.315572</td>
    </tr>
    <tr>
      <th>48</th>
      <td>M5L</td>
      <td>Downtown Toronto</td>
      <td>Commerce Court, Victoria Hotel</td>
      <td>43.648198</td>
      <td>-79.379817</td>
    </tr>
    <tr>
      <th>54</th>
      <td>M4M</td>
      <td>East Toronto</td>
      <td>Studio District</td>
      <td>43.659526</td>
      <td>-79.340923</td>
    </tr>
    <tr>
      <th>61</th>
      <td>M4N</td>
      <td>Central Toronto</td>
      <td>Lawrence Park</td>
      <td>43.728020</td>
      <td>-79.388790</td>
    </tr>
    <tr>
      <th>62</th>
      <td>M5N</td>
      <td>Central Toronto</td>
      <td>Roselawn</td>
      <td>43.711695</td>
      <td>-79.416936</td>
    </tr>
    <tr>
      <th>67</th>
      <td>M4P</td>
      <td>Central Toronto</td>
      <td>Davisville North</td>
      <td>43.712751</td>
      <td>-79.390197</td>
    </tr>
    <tr>
      <th>68</th>
      <td>M5P</td>
      <td>Central Toronto</td>
      <td>Forest Hill North &amp; West, Forest Hill Road Park</td>
      <td>43.696948</td>
      <td>-79.411307</td>
    </tr>
    <tr>
      <th>69</th>
      <td>M6P</td>
      <td>West Toronto</td>
      <td>High Park, The Junction South</td>
      <td>43.661608</td>
      <td>-79.464763</td>
    </tr>
    <tr>
      <th>73</th>
      <td>M4R</td>
      <td>Central Toronto</td>
      <td>North Toronto West, Lawrence Park</td>
      <td>43.715383</td>
      <td>-79.405678</td>
    </tr>
    <tr>
      <th>74</th>
      <td>M5R</td>
      <td>Central Toronto</td>
      <td>The Annex, North Midtown, Yorkville</td>
      <td>43.672710</td>
      <td>-79.405678</td>
    </tr>
    <tr>
      <th>75</th>
      <td>M6R</td>
      <td>West Toronto</td>
      <td>Parkdale, Roncesvalles</td>
      <td>43.648960</td>
      <td>-79.456325</td>
    </tr>
    <tr>
      <th>79</th>
      <td>M4S</td>
      <td>Central Toronto</td>
      <td>Davisville</td>
      <td>43.704324</td>
      <td>-79.388790</td>
    </tr>
    <tr>
      <th>80</th>
      <td>M5S</td>
      <td>Downtown Toronto</td>
      <td>University of Toronto, Harbord</td>
      <td>43.662696</td>
      <td>-79.400049</td>
    </tr>
    <tr>
      <th>81</th>
      <td>M6S</td>
      <td>West Toronto</td>
      <td>Runnymede, Swansea</td>
      <td>43.651571</td>
      <td>-79.484450</td>
    </tr>
    <tr>
      <th>83</th>
      <td>M4T</td>
      <td>Central Toronto</td>
      <td>Moore Park, Summerhill East</td>
      <td>43.689574</td>
      <td>-79.383160</td>
    </tr>
    <tr>
      <th>84</th>
      <td>M5T</td>
      <td>Downtown Toronto</td>
      <td>Kensington Market, Chinatown, Grange Park</td>
      <td>43.653206</td>
      <td>-79.400049</td>
    </tr>
    <tr>
      <th>86</th>
      <td>M4V</td>
      <td>Central Toronto</td>
      <td>Summerhill West, Rathnelly, South Hill, Forest...</td>
      <td>43.686412</td>
      <td>-79.400049</td>
    </tr>
    <tr>
      <th>87</th>
      <td>M5V</td>
      <td>Downtown Toronto</td>
      <td>CN Tower, King and Spadina, Railway Lands, Har...</td>
      <td>43.628947</td>
      <td>-79.394420</td>
    </tr>
    <tr>
      <th>91</th>
      <td>M4W</td>
      <td>Downtown Toronto</td>
      <td>Rosedale</td>
      <td>43.679563</td>
      <td>-79.377529</td>
    </tr>
    <tr>
      <th>92</th>
      <td>M5W</td>
      <td>Downtown Toronto</td>
      <td>Stn A PO Boxes</td>
      <td>43.646435</td>
      <td>-79.374846</td>
    </tr>
    <tr>
      <th>96</th>
      <td>M4X</td>
      <td>Downtown Toronto</td>
      <td>St. James Town, Cabbagetown</td>
      <td>43.667967</td>
      <td>-79.367675</td>
    </tr>
    <tr>
      <th>97</th>
      <td>M5X</td>
      <td>Downtown Toronto</td>
      <td>First Canadian Place, Underground city</td>
      <td>43.648429</td>
      <td>-79.382280</td>
    </tr>
    <tr>
      <th>99</th>
      <td>M4Y</td>
      <td>Downtown Toronto</td>
      <td>Church and Wellesley</td>
      <td>43.665860</td>
      <td>-79.383160</td>
    </tr>
    <tr>
      <th>100</th>
      <td>M7Y</td>
      <td>East Toronto</td>
      <td>Business reply mail Processing Centre, South C...</td>
      <td>43.662744</td>
      <td>-79.321558</td>
    </tr>
  </tbody>
</table>
</div>




```python
map_toronto = folium.Map(location=[43.651070,-79.347015],zoom_start=10)

for lat,lng,borough,neighbourhood in zip(df4['Latitude'],df4['Longitude'],df4['Borough'],df4['Neighbourhood']):
    label = '{}, {}'.format(neighbourhood, borough)
    label = folium.Popup(label, parse_html=True)
    folium.CircleMarker(
    [lat,lng],
    radius=5,
    popup=label,
    color='blue',
    fill=True,
    fill_color='#3186cc',
    fill_opacity=0.7,
    parse_html=False).add_to(map_toronto)
map_toronto
```




<div style="width:100%;"><div style="position:relative;width:100%;height:0;padding-bottom:60%;"><span style="color:#565656">Make this Notebook Trusted to load map: File -> Trust Notebook</span><iframe src="about:blank" style="position:absolute;width:100%;height:100%;left:0;top:0;border:none !important;" data-html=PCFET0NUWVBFIGh0bWw+CjxoZWFkPiAgICAKICAgIDxtZXRhIGh0dHAtZXF1aXY9ImNvbnRlbnQtdHlwZSIgY29udGVudD0idGV4dC9odG1sOyBjaGFyc2V0PVVURi04IiAvPgogICAgPHNjcmlwdD5MX1BSRUZFUl9DQU5WQVMgPSBmYWxzZTsgTF9OT19UT1VDSCA9IGZhbHNlOyBMX0RJU0FCTEVfM0QgPSBmYWxzZTs8L3NjcmlwdD4KICAgIDxzY3JpcHQgc3JjPSJodHRwczovL2Nkbi5qc2RlbGl2ci5uZXQvbnBtL2xlYWZsZXRAMS4yLjAvZGlzdC9sZWFmbGV0LmpzIj48L3NjcmlwdD4KICAgIDxzY3JpcHQgc3JjPSJodHRwczovL2FqYXguZ29vZ2xlYXBpcy5jb20vYWpheC9saWJzL2pxdWVyeS8xLjExLjEvanF1ZXJ5Lm1pbi5qcyI+PC9zY3JpcHQ+CiAgICA8c2NyaXB0IHNyYz0iaHR0cHM6Ly9tYXhjZG4uYm9vdHN0cmFwY2RuLmNvbS9ib290c3RyYXAvMy4yLjAvanMvYm9vdHN0cmFwLm1pbi5qcyI+PC9zY3JpcHQ+CiAgICA8c2NyaXB0IHNyYz0iaHR0cHM6Ly9jZG5qcy5jbG91ZGZsYXJlLmNvbS9hamF4L2xpYnMvTGVhZmxldC5hd2Vzb21lLW1hcmtlcnMvMi4wLjIvbGVhZmxldC5hd2Vzb21lLW1hcmtlcnMuanMiPjwvc2NyaXB0PgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL2Nkbi5qc2RlbGl2ci5uZXQvbnBtL2xlYWZsZXRAMS4yLjAvZGlzdC9sZWFmbGV0LmNzcyIvPgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL21heGNkbi5ib290c3RyYXBjZG4uY29tL2Jvb3RzdHJhcC8zLjIuMC9jc3MvYm9vdHN0cmFwLm1pbi5jc3MiLz4KICAgIDxsaW5rIHJlbD0ic3R5bGVzaGVldCIgaHJlZj0iaHR0cHM6Ly9tYXhjZG4uYm9vdHN0cmFwY2RuLmNvbS9ib290c3RyYXAvMy4yLjAvY3NzL2Jvb3RzdHJhcC10aGVtZS5taW4uY3NzIi8+CiAgICA8bGluayByZWw9InN0eWxlc2hlZXQiIGhyZWY9Imh0dHBzOi8vbWF4Y2RuLmJvb3RzdHJhcGNkbi5jb20vZm9udC1hd2Vzb21lLzQuNi4zL2Nzcy9mb250LWF3ZXNvbWUubWluLmNzcyIvPgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL2NkbmpzLmNsb3VkZmxhcmUuY29tL2FqYXgvbGlicy9MZWFmbGV0LmF3ZXNvbWUtbWFya2Vycy8yLjAuMi9sZWFmbGV0LmF3ZXNvbWUtbWFya2Vycy5jc3MiLz4KICAgIDxsaW5rIHJlbD0ic3R5bGVzaGVldCIgaHJlZj0iaHR0cHM6Ly9yYXdnaXQuY29tL3B5dGhvbi12aXN1YWxpemF0aW9uL2ZvbGl1bS9tYXN0ZXIvZm9saXVtL3RlbXBsYXRlcy9sZWFmbGV0LmF3ZXNvbWUucm90YXRlLmNzcyIvPgogICAgPHN0eWxlPmh0bWwsIGJvZHkge3dpZHRoOiAxMDAlO2hlaWdodDogMTAwJTttYXJnaW46IDA7cGFkZGluZzogMDt9PC9zdHlsZT4KICAgIDxzdHlsZT4jbWFwIHtwb3NpdGlvbjphYnNvbHV0ZTt0b3A6MDtib3R0b206MDtyaWdodDowO2xlZnQ6MDt9PC9zdHlsZT4KICAgIAogICAgICAgICAgICA8c3R5bGU+ICNtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEgewogICAgICAgICAgICAgICAgcG9zaXRpb24gOiByZWxhdGl2ZTsKICAgICAgICAgICAgICAgIHdpZHRoIDogMTAwLjAlOwogICAgICAgICAgICAgICAgaGVpZ2h0OiAxMDAuMCU7CiAgICAgICAgICAgICAgICBsZWZ0OiAwLjAlOwogICAgICAgICAgICAgICAgdG9wOiAwLjAlOwogICAgICAgICAgICAgICAgfQogICAgICAgICAgICA8L3N0eWxlPgogICAgICAgIAo8L2hlYWQ+Cjxib2R5PiAgICAKICAgIAogICAgICAgICAgICA8ZGl2IGNsYXNzPSJmb2xpdW0tbWFwIiBpZD0ibWFwXzZiZWNmMTkxZmI2NTQyNGE5OGM0M2I5OTZjYzkwMzFhIiA+PC9kaXY+CiAgICAgICAgCjwvYm9keT4KPHNjcmlwdD4gICAgCiAgICAKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGJvdW5kcyA9IG51bGw7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgdmFyIG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSA9IEwubWFwKAogICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgJ21hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYScsCiAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICB7Y2VudGVyOiBbNDMuNjUxMDcsLTc5LjM0NzAxNV0sCiAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICB6b29tOiAxMCwKICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgIG1heEJvdW5kczogYm91bmRzLAogICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgbGF5ZXJzOiBbXSwKICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgIHdvcmxkQ29weUp1bXA6IGZhbHNlLAogICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgY3JzOiBMLkNSUy5FUFNHMzg1NwogICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICB9KTsKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHRpbGVfbGF5ZXJfMWQ3NmMzOTU1MGY0NDQ3ZjkxNTBkYjU1MzVmZjc3YzggPSBMLnRpbGVMYXllcigKICAgICAgICAgICAgICAgICdodHRwczovL3tzfS50aWxlLm9wZW5zdHJlZXRtYXAub3JnL3t6fS97eH0ve3l9LnBuZycsCiAgICAgICAgICAgICAgICB7CiAgImF0dHJpYnV0aW9uIjogbnVsbCwKICAiZGV0ZWN0UmV0aW5hIjogZmFsc2UsCiAgIm1heFpvb20iOiAxOCwKICAibWluWm9vbSI6IDEsCiAgIm5vV3JhcCI6IGZhbHNlLAogICJzdWJkb21haW5zIjogImFiYyIKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEpOwogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzQxZDU5NTg0YWI2OTRiNGE5ODBkYzBhOWMwY2ViNDBjID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjU0MjU5OSwtNzkuMzYwNjM1OV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF8yOGQyMWM3MjRjMWQ0Njc2OTg3ODk2MWNjMTEyMjMwZiA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9mMjlmNWZhYTBiMGU0NmNhOTA3NWI5M2IwNGJjNWIzNiA9ICQoJzxkaXYgaWQ9Imh0bWxfZjI5ZjVmYWEwYjBlNDZjYTkwNzViOTNiMDRiYzViMzYiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPlJlZ2VudCBQYXJrLCBIYXJib3VyZnJvbnQsIERvd250b3duIFRvcm9udG88L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwXzI4ZDIxYzcyNGMxZDQ2NzY5ODc4OTYxY2MxMTIyMzBmLnNldENvbnRlbnQoaHRtbF9mMjlmNWZhYTBiMGU0NmNhOTA3NWI5M2IwNGJjNWIzNik7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl80MWQ1OTU4NGFiNjk0YjRhOTgwZGMwYTljMGNlYjQwYy5iaW5kUG9wdXAocG9wdXBfMjhkMjFjNzI0YzFkNDY3Njk4Nzg5NjFjYzExMjIzMGYpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfYmY3OTk5MWI0YzM2NDhjMTg5NTFiNmIzZjg3ZTQzZGMgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42NjIzMDE1LC03OS4zODk0OTM4XSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogImJsdWUiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjMzE4NmNjIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzZiZWNmMTkxZmI2NTQyNGE5OGM0M2I5OTZjYzkwMzFhKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzgwZGFhMTA1MTRmYTRlMTU4MGVlYzNkOTBhM2ZiN2VlID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sX2NhNjE1ZWU4NTljZDQ2YWY5MDUxNjMzYjY3N2FiMjFiID0gJCgnPGRpdiBpZD0iaHRtbF9jYTYxNWVlODU5Y2Q0NmFmOTA1MTYzM2I2NzdhYjIxYiIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+UXVlZW4mIzM5O3MgUGFyaywgT250YXJpbyBQcm92aW5jaWFsIEdvdmVybm1lbnQsIERvd250b3duIFRvcm9udG88L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwXzgwZGFhMTA1MTRmYTRlMTU4MGVlYzNkOTBhM2ZiN2VlLnNldENvbnRlbnQoaHRtbF9jYTYxNWVlODU5Y2Q0NmFmOTA1MTYzM2I2NzdhYjIxYik7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl9iZjc5OTkxYjRjMzY0OGMxODk1MWI2YjNmODdlNDNkYy5iaW5kUG9wdXAocG9wdXBfODBkYWExMDUxNGZhNGUxNTgwZWVjM2Q5MGEzZmI3ZWUpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfZDBmYTNkZjBiNGY5NDU4ZTgzNjgxODUwMDU3NGJkYmYgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42NTcxNjE4LC03OS4zNzg5MzcwOTk5OTk5OV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF80MTMyNGRiMGNiNDc0MjUxYmYwMzhjMmY4Mjg4Yjk5NyA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9iYjFiYmZjZDQ3NTU0YzAxOGRhYmM4ZTc2OWMzOGZlYyA9ICQoJzxkaXYgaWQ9Imh0bWxfYmIxYmJmY2Q0NzU1NGMwMThkYWJjOGU3NjljMzhmZWMiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPkdhcmRlbiBEaXN0cmljdCwgUnllcnNvbiwgRG93bnRvd24gVG9yb250bzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfNDEzMjRkYjBjYjQ3NDI1MWJmMDM4YzJmODI4OGI5OTcuc2V0Q29udGVudChodG1sX2JiMWJiZmNkNDc1NTRjMDE4ZGFiYzhlNzY5YzM4ZmVjKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyX2QwZmEzZGYwYjRmOTQ1OGU4MzY4MTg1MDA1NzRiZGJmLmJpbmRQb3B1cChwb3B1cF80MTMyNGRiMGNiNDc0MjUxYmYwMzhjMmY4Mjg4Yjk5Nyk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9iNWE4YjE2OTI1MTA0ODY4ODMzODRmNTRjN2NkYTA3MyA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY1MTQ5MzksLTc5LjM3NTQxNzldLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiYmx1ZSIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMzMTg2Y2MiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfNDY1MDMyYzFhNDA1NDVmZmE1ZjhhNDAyMzk4NDIwYmIgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfYTBlYWU4NDQyZjEyNDRlYzliNmUwZTU1MGZjNDVhNjkgPSAkKCc8ZGl2IGlkPSJodG1sX2EwZWFlODQ0MmYxMjQ0ZWM5YjZlMGU1NTBmYzQ1YTY5IiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5TdC4gSmFtZXMgVG93biwgRG93bnRvd24gVG9yb250bzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfNDY1MDMyYzFhNDA1NDVmZmE1ZjhhNDAyMzk4NDIwYmIuc2V0Q29udGVudChodG1sX2EwZWFlODQ0MmYxMjQ0ZWM5YjZlMGU1NTBmYzQ1YTY5KTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyX2I1YThiMTY5MjUxMDQ4Njg4MzM4NGY1NGM3Y2RhMDczLmJpbmRQb3B1cChwb3B1cF80NjUwMzJjMWE0MDU0NWZmYTVmOGE0MDIzOTg0MjBiYik7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9hOWM0OWVkOGQ2NWE0NTNiYTU5MzAyZTAzYWUxYmQ4YiA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY3NjM1NzM5OTk5OTk5LC03OS4yOTMwMzEyXSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogImJsdWUiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjMzE4NmNjIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzZiZWNmMTkxZmI2NTQyNGE5OGM0M2I5OTZjYzkwMzFhKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzAyYWVmYWI5MzdmODQ5YzY5OTY0ZDQxZDNkMGRjMWM0ID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzhiNzI2MDBmNmQxYjRkNGY5ZDQ1N2JmY2NkMDliYTk1ID0gJCgnPGRpdiBpZD0iaHRtbF84YjcyNjAwZjZkMWI0ZDRmOWQ0NTdiZmNjZDA5YmE5NSIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+VGhlIEJlYWNoZXMsIEVhc3QgVG9yb250bzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfMDJhZWZhYjkzN2Y4NDljNjk5NjRkNDFkM2QwZGMxYzQuc2V0Q29udGVudChodG1sXzhiNzI2MDBmNmQxYjRkNGY5ZDQ1N2JmY2NkMDliYTk1KTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyX2E5YzQ5ZWQ4ZDY1YTQ1M2JhNTkzMDJlMDNhZTFiZDhiLmJpbmRQb3B1cChwb3B1cF8wMmFlZmFiOTM3Zjg0OWM2OTk2NGQ0MWQzZDBkYzFjNCk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl83YjE3MDA4MWJmZDk0MDNlYmJmZjdjNDllYzVmZmI3OSA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY0NDc3MDc5OTk5OTk5NiwtNzkuMzczMzA2NF0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9kMWJiZWMwOGQxYTQ0MmRkOTMwYWQ2MmRlNDEyODc0OCA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF8wYjFjM2ZiZjIzZDc0NDEwODBiNzJiMDllYmJiZTNlNCA9ICQoJzxkaXYgaWQ9Imh0bWxfMGIxYzNmYmYyM2Q3NDQxMDgwYjcyYjA5ZWJiYmUzZTQiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPkJlcmN6eSBQYXJrLCBEb3dudG93biBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF9kMWJiZWMwOGQxYTQ0MmRkOTMwYWQ2MmRlNDEyODc0OC5zZXRDb250ZW50KGh0bWxfMGIxYzNmYmYyM2Q3NDQxMDgwYjcyYjA5ZWJiYmUzZTQpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfN2IxNzAwODFiZmQ5NDAzZWJiZmY3YzQ5ZWM1ZmZiNzkuYmluZFBvcHVwKHBvcHVwX2QxYmJlYzA4ZDFhNDQyZGQ5MzBhZDYyZGU0MTI4NzQ4KTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzc5ZDAwODdkNmI1MDQ3ZWE4MWMxNGYzYmQxMTU1NzkwID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjU3OTUyNCwtNzkuMzg3MzgyNl0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9jOGVkZDYwYzI2ZWI0ZDUzYjJkMjVlZDZlNzNkZDc2NyA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF8yOGZjZGFjYTU2ZjU0ODJiOTViZDFmMGI4YTAxZjVkZCA9ICQoJzxkaXYgaWQ9Imh0bWxfMjhmY2RhY2E1NmY1NDgyYjk1YmQxZjBiOGEwMWY1ZGQiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPkNlbnRyYWwgQmF5IFN0cmVldCwgRG93bnRvd24gVG9yb250bzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfYzhlZGQ2MGMyNmViNGQ1M2IyZDI1ZWQ2ZTczZGQ3Njcuc2V0Q29udGVudChodG1sXzI4ZmNkYWNhNTZmNTQ4MmI5NWJkMWYwYjhhMDFmNWRkKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzc5ZDAwODdkNmI1MDQ3ZWE4MWMxNGYzYmQxMTU1NzkwLmJpbmRQb3B1cChwb3B1cF9jOGVkZDYwYzI2ZWI0ZDUzYjJkMjVlZDZlNzNkZDc2Nyk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl8xMzEyOWI4YTFmOTc0MDY5YWNkNTQwMmJkZGZjMTAyNSA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY2OTU0MiwtNzkuNDIyNTYzN10sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9mZGQyMzljODFiMmE0YjRjYTJmZGJiM2E1NjJkOTIxZiA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF85MzQ5OGVlOWI5ZWY0YWUzOTAzYWJlNjNjMDM3YWNmOSA9ICQoJzxkaXYgaWQ9Imh0bWxfOTM0OThlZTliOWVmNGFlMzkwM2FiZTYzYzAzN2FjZjkiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPkNocmlzdGllLCBEb3dudG93biBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF9mZGQyMzljODFiMmE0YjRjYTJmZGJiM2E1NjJkOTIxZi5zZXRDb250ZW50KGh0bWxfOTM0OThlZTliOWVmNGFlMzkwM2FiZTYzYzAzN2FjZjkpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfMTMxMjliOGExZjk3NDA2OWFjZDU0MDJiZGRmYzEwMjUuYmluZFBvcHVwKHBvcHVwX2ZkZDIzOWM4MWIyYTRiNGNhMmZkYmIzYTU2MmQ5MjFmKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyX2IxMjkxNGM2YzQ5NjQ1MGE5YjhkN2RjN2I2NjA0NzRiID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjUwNTcxMjAwMDAwMDEsLTc5LjM4NDU2NzVdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiYmx1ZSIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMzMTg2Y2MiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfY2E4MWFkNDVmMWFhNGRmNzliMjU0MWVmOTA4ZDFiNjYgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfYTkxMWQzZTgxZjg4NGM2ZWExNGRmMjUzMTFhNzFlZWMgPSAkKCc8ZGl2IGlkPSJodG1sX2E5MTFkM2U4MWY4ODRjNmVhMTRkZjI1MzExYTcxZWVjIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5SaWNobW9uZCwgQWRlbGFpZGUsIEtpbmcsIERvd250b3duIFRvcm9udG88L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwX2NhODFhZDQ1ZjFhYTRkZjc5YjI1NDFlZjkwOGQxYjY2LnNldENvbnRlbnQoaHRtbF9hOTExZDNlODFmODg0YzZlYTE0ZGYyNTMxMWE3MWVlYyk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl9iMTI5MTRjNmM0OTY0NTBhOWI4ZDdkYzdiNjYwNDc0Yi5iaW5kUG9wdXAocG9wdXBfY2E4MWFkNDVmMWFhNGRmNzliMjU0MWVmOTA4ZDFiNjYpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfOWUxNGZlMGJhYmI0NGZiY2JlYTQ5ZTA1NGY2MmEyMmMgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42NjkwMDUxMDAwMDAwMSwtNzkuNDQyMjU5M10sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF82MTgxN2NiNmViOTc0MDQwOTBkNzg4YmI2NDBjZjk1NiA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF82M2RjMWFhYzIyMDU0NDI0YWVlMGViZWEwMDdhMjg5NiA9ICQoJzxkaXYgaWQ9Imh0bWxfNjNkYzFhYWMyMjA1NDQyNGFlZTBlYmVhMDA3YTI4OTYiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPkR1ZmZlcmluLCBEb3ZlcmNvdXJ0IFZpbGxhZ2UsIFdlc3QgVG9yb250bzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfNjE4MTdjYjZlYjk3NDA0MDkwZDc4OGJiNjQwY2Y5NTYuc2V0Q29udGVudChodG1sXzYzZGMxYWFjMjIwNTQ0MjRhZWUwZWJlYTAwN2EyODk2KTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzllMTRmZTBiYWJiNDRmYmNiZWE0OWUwNTRmNjJhMjJjLmJpbmRQb3B1cChwb3B1cF82MTgxN2NiNmViOTc0MDQwOTBkNzg4YmI2NDBjZjk1Nik7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl80ZTI1MTNiZmRmNGM0OTAzOWZlYzcxYjZiZjMzNDg0NiA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY0MDgxNTcsLTc5LjM4MTc1MjI5OTk5OTk5XSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogImJsdWUiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjMzE4NmNjIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzZiZWNmMTkxZmI2NTQyNGE5OGM0M2I5OTZjYzkwMzFhKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwX2Q0ZWYxMjE0MDIzYTQzOTBiODcxY2YwMjU0OGY5Y2NlID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzc4ZmE4ZDE2NWRiYTRjMTFiOTkyMGQwY2YxNDc4ODBiID0gJCgnPGRpdiBpZD0iaHRtbF83OGZhOGQxNjVkYmE0YzExYjk5MjBkMGNmMTQ3ODgwYiIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+SGFyYm91cmZyb250IEVhc3QsIFVuaW9uIFN0YXRpb24sIFRvcm9udG8gSXNsYW5kcywgRG93bnRvd24gVG9yb250bzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfZDRlZjEyMTQwMjNhNDM5MGI4NzFjZjAyNTQ4ZjljY2Uuc2V0Q29udGVudChodG1sXzc4ZmE4ZDE2NWRiYTRjMTFiOTkyMGQwY2YxNDc4ODBiKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzRlMjUxM2JmZGY0YzQ5MDM5ZmVjNzFiNmJmMzM0ODQ2LmJpbmRQb3B1cChwb3B1cF9kNGVmMTIxNDAyM2E0MzkwYjg3MWNmMDI1NDhmOWNjZSk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl85ZTRhZjNlNWQ2ODc0NTlkYmY4MDE5OTcyZWYwYzc3NiA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY0NzkyNjcwMDAwMDAwNiwtNzkuNDE5NzQ5N10sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF8zNjgyMjMxM2FhOTI0ZmE2OTg4NmE0NjQ5MmNiN2MxNSA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9kOWViMDczYjYwNjQ0MGNlOWQ3ODliNmQxNTAxNjRjOSA9ICQoJzxkaXYgaWQ9Imh0bWxfZDllYjA3M2I2MDY0NDBjZTlkNzg5YjZkMTUwMTY0YzkiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPkxpdHRsZSBQb3J0dWdhbCwgVHJpbml0eSwgV2VzdCBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF8zNjgyMjMxM2FhOTI0ZmE2OTg4NmE0NjQ5MmNiN2MxNS5zZXRDb250ZW50KGh0bWxfZDllYjA3M2I2MDY0NDBjZTlkNzg5YjZkMTUwMTY0YzkpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfOWU0YWYzZTVkNjg3NDU5ZGJmODAxOTk3MmVmMGM3NzYuYmluZFBvcHVwKHBvcHVwXzM2ODIyMzEzYWE5MjRmYTY5ODg2YTQ2NDkyY2I3YzE1KTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzMzMmU0YTM3ZmZkMzQ0NjJiNjc1NTg4MDIwM2Y2ZGY4ID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjc5NTU3MSwtNzkuMzUyMTg4XSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogImJsdWUiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjMzE4NmNjIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzZiZWNmMTkxZmI2NTQyNGE5OGM0M2I5OTZjYzkwMzFhKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwX2UxMDM4ODliNDAzYzRmYzE5YWFkZTEwMzdjNWI5ZWJiID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sX2M3ZjQzOGQ2NGY5NjRiODM4NTRlMDIxZDkxYzRkNTY4ID0gJCgnPGRpdiBpZD0iaHRtbF9jN2Y0MzhkNjRmOTY0YjgzODU0ZTAyMWQ5MWM0ZDU2OCIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+VGhlIERhbmZvcnRoIFdlc3QsIFJpdmVyZGFsZSwgRWFzdCBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF9lMTAzODg5YjQwM2M0ZmMxOWFhZGUxMDM3YzViOWViYi5zZXRDb250ZW50KGh0bWxfYzdmNDM4ZDY0Zjk2NGI4Mzg1NGUwMjFkOTFjNGQ1NjgpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfMzMyZTRhMzdmZmQzNDQ2MmI2NzU1ODgwMjAzZjZkZjguYmluZFBvcHVwKHBvcHVwX2UxMDM4ODliNDAzYzRmYzE5YWFkZTEwMzdjNWI5ZWJiKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzhmYWM5YzkyYzE2MTQwMzNiY2QyYjBjZDBjYmEwZDg1ID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjQ3MTc2OCwtNzkuMzgxNTc2NDAwMDAwMDFdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiYmx1ZSIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMzMTg2Y2MiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfYjg5MTFhMTE0ZTE0NDMwNDkzMjFhNDNjZjIzNDBlM2EgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfMmE3ZDE1MjkzYjQ5NDQyMmEzZjk4YzY2ZDg5ZDVhN2QgPSAkKCc8ZGl2IGlkPSJodG1sXzJhN2QxNTI5M2I0OTQ0MjJhM2Y5OGM2NmQ4OWQ1YTdkIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5Ub3JvbnRvIERvbWluaW9uIENlbnRyZSwgRGVzaWduIEV4Y2hhbmdlLCBEb3dudG93biBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF9iODkxMWExMTRlMTQ0MzA0OTMyMWE0M2NmMjM0MGUzYS5zZXRDb250ZW50KGh0bWxfMmE3ZDE1MjkzYjQ5NDQyMmEzZjk4YzY2ZDg5ZDVhN2QpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfOGZhYzljOTJjMTYxNDAzM2JjZDJiMGNkMGNiYTBkODUuYmluZFBvcHVwKHBvcHVwX2I4OTExYTExNGUxNDQzMDQ5MzIxYTQzY2YyMzQwZTNhKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzgyNWU0NTc3YWNjZTQ2MDRiNzczYzc0OTRjYmM0ZTY3ID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjM2ODQ3MiwtNzkuNDI4MTkxNDAwMDAwMDJdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiYmx1ZSIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMzMTg2Y2MiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfYzViYzNjZGE4YmQyNDNhOGEyNDQwZDdlZjNkNjRjNzcgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfMDEwY2NlZjc3YTZlNGE5OGI2ZmM5NjBiMmRhZGE1N2IgPSAkKCc8ZGl2IGlkPSJodG1sXzAxMGNjZWY3N2E2ZTRhOThiNmZjOTYwYjJkYWRhNTdiIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5Ccm9ja3RvbiwgUGFya2RhbGUgVmlsbGFnZSwgRXhoaWJpdGlvbiBQbGFjZSwgV2VzdCBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF9jNWJjM2NkYThiZDI0M2E4YTI0NDBkN2VmM2Q2NGM3Ny5zZXRDb250ZW50KGh0bWxfMDEwY2NlZjc3YTZlNGE5OGI2ZmM5NjBiMmRhZGE1N2IpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfODI1ZTQ1NzdhY2NlNDYwNGI3NzNjNzQ5NGNiYzRlNjcuYmluZFBvcHVwKHBvcHVwX2M1YmMzY2RhOGJkMjQzYThhMjQ0MGQ3ZWYzZDY0Yzc3KTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyX2Q2NWY2ODM2NjA2MjQ1NjQ5MDE2YjQ3M2E0NDIzNTcyID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjY4OTk4NSwtNzkuMzE1NTcxNTk5OTk5OThdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiYmx1ZSIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMzMTg2Y2MiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfMGYzOWFkOTQ3MjE5NDE1ZDg5ZWY0NDY2MTJlZWQ1NWQgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfMTEyMmY3ODUwZjg1NDk5NWI1NDg2NjFiYzA2Zjk2MDAgPSAkKCc8ZGl2IGlkPSJodG1sXzExMjJmNzg1MGY4NTQ5OTViNTQ4NjYxYmMwNmY5NjAwIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5JbmRpYSBCYXphYXIsIFRoZSBCZWFjaGVzIFdlc3QsIEVhc3QgVG9yb250bzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfMGYzOWFkOTQ3MjE5NDE1ZDg5ZWY0NDY2MTJlZWQ1NWQuc2V0Q29udGVudChodG1sXzExMjJmNzg1MGY4NTQ5OTViNTQ4NjYxYmMwNmY5NjAwKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyX2Q2NWY2ODM2NjA2MjQ1NjQ5MDE2YjQ3M2E0NDIzNTcyLmJpbmRQb3B1cChwb3B1cF8wZjM5YWQ5NDcyMTk0MTVkODllZjQ0NjYxMmVlZDU1ZCk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl85N2FlYzU4OGVjNmY0MWU3OTk3M2VmNTRmMGVmOWU0OCA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY0ODE5ODUsLTc5LjM3OTgxNjkwMDAwMDAxXSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogImJsdWUiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjMzE4NmNjIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzZiZWNmMTkxZmI2NTQyNGE5OGM0M2I5OTZjYzkwMzFhKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwX2YzNmFlMDQ3NTI4YTRlYjg4YWU3NmMwOWI1MzcyYmY3ID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzllZjZmYTUxYTgzMTQ1OTk4ZWJkZGU2ZDM5NDdiMTgyID0gJCgnPGRpdiBpZD0iaHRtbF85ZWY2ZmE1MWE4MzE0NTk5OGViZGRlNmQzOTQ3YjE4MiIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+Q29tbWVyY2UgQ291cnQsIFZpY3RvcmlhIEhvdGVsLCBEb3dudG93biBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF9mMzZhZTA0NzUyOGE0ZWI4OGFlNzZjMDliNTM3MmJmNy5zZXRDb250ZW50KGh0bWxfOWVmNmZhNTFhODMxNDU5OThlYmRkZTZkMzk0N2IxODIpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfOTdhZWM1ODhlYzZmNDFlNzk5NzNlZjU0ZjBlZjllNDguYmluZFBvcHVwKHBvcHVwX2YzNmFlMDQ3NTI4YTRlYjg4YWU3NmMwOWI1MzcyYmY3KTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzQ1NjMxNWFhMTMxYzQ4OWM4NTM3NmM5Y2FlNmYwNTdlID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjU5NTI1NSwtNzkuMzQwOTIzXSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogImJsdWUiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjMzE4NmNjIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzZiZWNmMTkxZmI2NTQyNGE5OGM0M2I5OTZjYzkwMzFhKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwX2RlYTg0NWY4OWRlNDQxZDdhOTUxYzU1Y2JhMmJlODQ2ID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzdkM2RiOTVjZWY3ODQzN2Y5OGIxY2IxZDVmN2IwYTcxID0gJCgnPGRpdiBpZD0iaHRtbF83ZDNkYjk1Y2VmNzg0MzdmOThiMWNiMWQ1ZjdiMGE3MSIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+U3R1ZGlvIERpc3RyaWN0LCBFYXN0IFRvcm9udG88L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwX2RlYTg0NWY4OWRlNDQxZDdhOTUxYzU1Y2JhMmJlODQ2LnNldENvbnRlbnQoaHRtbF83ZDNkYjk1Y2VmNzg0MzdmOThiMWNiMWQ1ZjdiMGE3MSk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl80NTYzMTVhYTEzMWM0ODljODUzNzZjOWNhZTZmMDU3ZS5iaW5kUG9wdXAocG9wdXBfZGVhODQ1Zjg5ZGU0NDFkN2E5NTFjNTVjYmEyYmU4NDYpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfMTE0NDEyOTE2MzE1NDA3OTk4OWM1ZTU3YjdhYWE3ZTMgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My43MjgwMjA1LC03OS4zODg3OTAxXSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogImJsdWUiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjMzE4NmNjIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzZiZWNmMTkxZmI2NTQyNGE5OGM0M2I5OTZjYzkwMzFhKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzg3NjEwNWMyMDM1ODRjYjZhMWM4ZDZjN2IxMDZiYmRiID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sX2IzM2I5OGZjM2JiOTQ3MjFhODU5OGNiMWYzYmNjYzk1ID0gJCgnPGRpdiBpZD0iaHRtbF9iMzNiOThmYzNiYjk0NzIxYTg1OThjYjFmM2JjY2M5NSIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+TGF3cmVuY2UgUGFyaywgQ2VudHJhbCBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF84NzYxMDVjMjAzNTg0Y2I2YTFjOGQ2YzdiMTA2YmJkYi5zZXRDb250ZW50KGh0bWxfYjMzYjk4ZmMzYmI5NDcyMWE4NTk4Y2IxZjNiY2NjOTUpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfMTE0NDEyOTE2MzE1NDA3OTk4OWM1ZTU3YjdhYWE3ZTMuYmluZFBvcHVwKHBvcHVwXzg3NjEwNWMyMDM1ODRjYjZhMWM4ZDZjN2IxMDZiYmRiKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzU5MjE1ZTA0ZDljZDQ0OGY4ZGUxNDE4MjZiMDFhYzk3ID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNzExNjk0OCwtNzkuNDE2OTM1NTk5OTk5OTldLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiYmx1ZSIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMzMTg2Y2MiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfY2E4NDEwYzE1ZjgyNGFhZjk3YmFmMzJkOTRiMDRlODUgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfMGZiNTFkMTA0ZWZkNDlkYTgwNmNmYzhmNjVhZTdhOTUgPSAkKCc8ZGl2IGlkPSJodG1sXzBmYjUxZDEwNGVmZDQ5ZGE4MDZjZmM4ZjY1YWU3YTk1IiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5Sb3NlbGF3biwgQ2VudHJhbCBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF9jYTg0MTBjMTVmODI0YWFmOTdiYWYzMmQ5NGIwNGU4NS5zZXRDb250ZW50KGh0bWxfMGZiNTFkMTA0ZWZkNDlkYTgwNmNmYzhmNjVhZTdhOTUpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfNTkyMTVlMDRkOWNkNDQ4ZjhkZTE0MTgyNmIwMWFjOTcuYmluZFBvcHVwKHBvcHVwX2NhODQxMGMxNWY4MjRhYWY5N2JhZjMyZDk0YjA0ZTg1KTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzE2MDQ1YjAxMWIwZjQ1ODdhMDM2MjRmODEyOTNjZWEzID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNzEyNzUxMSwtNzkuMzkwMTk3NV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF84MWUzNmNlN2RmMzk0Mjk2YmE0NGU3YTRkNzM0ODZiNiA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF85MjdlY2Q1ZTU2YmQ0NTZiOTMyYTZiYjBiNmQ3ZTEyZCA9ICQoJzxkaXYgaWQ9Imh0bWxfOTI3ZWNkNWU1NmJkNDU2YjkzMmE2YmIwYjZkN2UxMmQiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPkRhdmlzdmlsbGUgTm9ydGgsIENlbnRyYWwgVG9yb250bzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfODFlMzZjZTdkZjM5NDI5NmJhNDRlN2E0ZDczNDg2YjYuc2V0Q29udGVudChodG1sXzkyN2VjZDVlNTZiZDQ1NmI5MzJhNmJiMGI2ZDdlMTJkKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzE2MDQ1YjAxMWIwZjQ1ODdhMDM2MjRmODEyOTNjZWEzLmJpbmRQb3B1cChwb3B1cF84MWUzNmNlN2RmMzk0Mjk2YmE0NGU3YTRkNzM0ODZiNik7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9kYzNmOTNlYWY4MTY0ODRiOTg2NTlkOTI4YWU1MmM1ZiA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY5Njk0NzYsLTc5LjQxMTMwNzIwMDAwMDAxXSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogImJsdWUiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjMzE4NmNjIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzZiZWNmMTkxZmI2NTQyNGE5OGM0M2I5OTZjYzkwMzFhKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzIwYjYyYjhlMjcwZTQzMWRhY2FkOTQ0ZTQ5Nzk4ZGE0ID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzIzYTU5NjBiNWY3NTQwN2Q5Njg1OTBkYTdhNzg2Njg2ID0gJCgnPGRpdiBpZD0iaHRtbF8yM2E1OTYwYjVmNzU0MDdkOTY4NTkwZGE3YTc4NjY4NiIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+Rm9yZXN0IEhpbGwgTm9ydGggJmFtcDsgV2VzdCwgRm9yZXN0IEhpbGwgUm9hZCBQYXJrLCBDZW50cmFsIFRvcm9udG88L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwXzIwYjYyYjhlMjcwZTQzMWRhY2FkOTQ0ZTQ5Nzk4ZGE0LnNldENvbnRlbnQoaHRtbF8yM2E1OTYwYjVmNzU0MDdkOTY4NTkwZGE3YTc4NjY4Nik7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl9kYzNmOTNlYWY4MTY0ODRiOTg2NTlkOTI4YWU1MmM1Zi5iaW5kUG9wdXAocG9wdXBfMjBiNjJiOGUyNzBlNDMxZGFjYWQ5NDRlNDk3OThkYTQpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfMTNhMzAxOWQ4YWJjNDBkZTk1MjNhOTQ5MjNmMDhiZmEgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42NjE2MDgzLC03OS40NjQ3NjMyOTk5OTk5OV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9iMzk3ODBlNGIwNTk0ODM2YmI1YzFlOGQxNTVmZDk3MyA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF8wZTVkMzQ5MmFjNzg0NjNjYmExNWJjNGMxZTU2MzcwYyA9ICQoJzxkaXYgaWQ9Imh0bWxfMGU1ZDM0OTJhYzc4NDYzY2JhMTViYzRjMWU1NjM3MGMiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPkhpZ2ggUGFyaywgVGhlIEp1bmN0aW9uIFNvdXRoLCBXZXN0IFRvcm9udG88L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwX2IzOTc4MGU0YjA1OTQ4MzZiYjVjMWU4ZDE1NWZkOTczLnNldENvbnRlbnQoaHRtbF8wZTVkMzQ5MmFjNzg0NjNjYmExNWJjNGMxZTU2MzcwYyk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl8xM2EzMDE5ZDhhYmM0MGRlOTUyM2E5NDkyM2YwOGJmYS5iaW5kUG9wdXAocG9wdXBfYjM5NzgwZTRiMDU5NDgzNmJiNWMxZThkMTU1ZmQ5NzMpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfNWExMGRhMjIzNjdlNDVkM2FiNDgyNGQ5OGU5Nzk1ZTcgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My43MTUzODM0LC03OS40MDU2Nzg0MDAwMDAwMV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9lZTM2MmI2ZGI3NzU0ZmZlYWU4YTBjMzVlM2ZhYWYyMiA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF84MjM5MGUyMjExOTk0Nzk0Yjk1MDJiNWRhZjQ5ZDc4MyA9ICQoJzxkaXYgaWQ9Imh0bWxfODIzOTBlMjIxMTk5NDc5NGI5NTAyYjVkYWY0OWQ3ODMiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPk5vcnRoIFRvcm9udG8gV2VzdCwgTGF3cmVuY2UgUGFyaywgQ2VudHJhbCBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF9lZTM2MmI2ZGI3NzU0ZmZlYWU4YTBjMzVlM2ZhYWYyMi5zZXRDb250ZW50KGh0bWxfODIzOTBlMjIxMTk5NDc5NGI5NTAyYjVkYWY0OWQ3ODMpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfNWExMGRhMjIzNjdlNDVkM2FiNDgyNGQ5OGU5Nzk1ZTcuYmluZFBvcHVwKHBvcHVwX2VlMzYyYjZkYjc3NTRmZmVhZThhMGMzNWUzZmFhZjIyKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzZmYTI0ZTZhODc3ZTQyZDI5ZWE4NjEzMGMxNGQ1ZmFlID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjcyNzA5NywtNzkuNDA1Njc4NDAwMDAwMDFdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiYmx1ZSIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMzMTg2Y2MiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfOGJmMTMyOTQ0MTc0NDMwZTlmMDRiODliYjg2Njc5NmIgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfNGFhN2YxOWIzNGZjNGJkNjhiNjAyMDhhNzFmYjBiMDAgPSAkKCc8ZGl2IGlkPSJodG1sXzRhYTdmMTliMzRmYzRiZDY4YjYwMjA4YTcxZmIwYjAwIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5UaGUgQW5uZXgsIE5vcnRoIE1pZHRvd24sIFlvcmt2aWxsZSwgQ2VudHJhbCBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF84YmYxMzI5NDQxNzQ0MzBlOWYwNGI4OWJiODY2Nzk2Yi5zZXRDb250ZW50KGh0bWxfNGFhN2YxOWIzNGZjNGJkNjhiNjAyMDhhNzFmYjBiMDApOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfNmZhMjRlNmE4NzdlNDJkMjllYTg2MTMwYzE0ZDVmYWUuYmluZFBvcHVwKHBvcHVwXzhiZjEzMjk0NDE3NDQzMGU5ZjA0Yjg5YmI4NjY3OTZiKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzkyOTY1NDgxYTQyYTQyNDRhZGIzYjBmNjgwNzgxYjZjID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjQ4OTU5NywtNzkuNDU2MzI1XSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogImJsdWUiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjMzE4NmNjIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzZiZWNmMTkxZmI2NTQyNGE5OGM0M2I5OTZjYzkwMzFhKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzI1NDRjM2Q2ZDNhYTRlY2Q5ZDhhZDdiNGUwNDRiNmY3ID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzJiYTFlM2IyOTE1MjRjZmI4OWVmNjEwZjFlYmM4ZGEwID0gJCgnPGRpdiBpZD0iaHRtbF8yYmExZTNiMjkxNTI0Y2ZiODllZjYxMGYxZWJjOGRhMCIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+UGFya2RhbGUsIFJvbmNlc3ZhbGxlcywgV2VzdCBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF8yNTQ0YzNkNmQzYWE0ZWNkOWQ4YWQ3YjRlMDQ0YjZmNy5zZXRDb250ZW50KGh0bWxfMmJhMWUzYjI5MTUyNGNmYjg5ZWY2MTBmMWViYzhkYTApOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfOTI5NjU0ODFhNDJhNDI0NGFkYjNiMGY2ODA3ODFiNmMuYmluZFBvcHVwKHBvcHVwXzI1NDRjM2Q2ZDNhYTRlY2Q5ZDhhZDdiNGUwNDRiNmY3KTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzgwZTcwNGI5YzgxNjQ3Y2JhMGU1MmE0MTdhOTM0ZTNhID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNzA0MzI0NCwtNzkuMzg4NzkwMV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF80ZDA2OGFjYWVlMDg0YTFjODE2NjY3ZjE5MWE4MzFhYiA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9lYTk2OWIyMGUyOTM0NmJhOGFmMjdlMzM2MTU5ZjQ1NyA9ICQoJzxkaXYgaWQ9Imh0bWxfZWE5NjliMjBlMjkzNDZiYThhZjI3ZTMzNjE1OWY0NTciIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPkRhdmlzdmlsbGUsIENlbnRyYWwgVG9yb250bzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfNGQwNjhhY2FlZTA4NGExYzgxNjY2N2YxOTFhODMxYWIuc2V0Q29udGVudChodG1sX2VhOTY5YjIwZTI5MzQ2YmE4YWYyN2UzMzYxNTlmNDU3KTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzgwZTcwNGI5YzgxNjQ3Y2JhMGU1MmE0MTdhOTM0ZTNhLmJpbmRQb3B1cChwb3B1cF80ZDA2OGFjYWVlMDg0YTFjODE2NjY3ZjE5MWE4MzFhYik7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl8wNjdkNTM4MTA4ZDk0MmRjOTg4NGZmYTQzNmI3N2ZhYiA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY2MjY5NTYsLTc5LjQwMDA0OTNdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiYmx1ZSIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMzMTg2Y2MiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfNzliOWJjNmQ2ZmNiNGQ0OGEzYTI5NGI1ZWNiYWFkMTMgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfNzE0NjQyNDdkN2NmNDQ4Y2I1YTQ4ZWJjMWM5OGIyYmEgPSAkKCc8ZGl2IGlkPSJodG1sXzcxNDY0MjQ3ZDdjZjQ0OGNiNWE0OGViYzFjOThiMmJhIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5Vbml2ZXJzaXR5IG9mIFRvcm9udG8sIEhhcmJvcmQsIERvd250b3duIFRvcm9udG88L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwXzc5YjliYzZkNmZjYjRkNDhhM2EyOTRiNWVjYmFhZDEzLnNldENvbnRlbnQoaHRtbF83MTQ2NDI0N2Q3Y2Y0NDhjYjVhNDhlYmMxYzk4YjJiYSk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl8wNjdkNTM4MTA4ZDk0MmRjOTg4NGZmYTQzNmI3N2ZhYi5iaW5kUG9wdXAocG9wdXBfNzliOWJjNmQ2ZmNiNGQ0OGEzYTI5NGI1ZWNiYWFkMTMpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfNjA1ZjdhZGEyOWEzNDJlZGEzY2MzYTgzZGQ3NTJkYjUgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42NTE1NzA2LC03OS40ODQ0NDk5XSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogImJsdWUiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjMzE4NmNjIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzZiZWNmMTkxZmI2NTQyNGE5OGM0M2I5OTZjYzkwMzFhKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwX2Y3MzliZTQ5MWU3YzRmZmI4YjE2YjNjM2NlMzIyYzVkID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sX2ZlMTFiZGMyNGMxNjRjYTQ5MDJmMDBlZjM3MjNiNTIzID0gJCgnPGRpdiBpZD0iaHRtbF9mZTExYmRjMjRjMTY0Y2E0OTAyZjAwZWYzNzIzYjUyMyIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+UnVubnltZWRlLCBTd2Fuc2VhLCBXZXN0IFRvcm9udG88L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwX2Y3MzliZTQ5MWU3YzRmZmI4YjE2YjNjM2NlMzIyYzVkLnNldENvbnRlbnQoaHRtbF9mZTExYmRjMjRjMTY0Y2E0OTAyZjAwZWYzNzIzYjUyMyk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl82MDVmN2FkYTI5YTM0MmVkYTNjYzNhODNkZDc1MmRiNS5iaW5kUG9wdXAocG9wdXBfZjczOWJlNDkxZTdjNGZmYjhiMTZiM2MzY2UzMjJjNWQpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfZmY0NWRmMDQ5Zjk0NGNmNGEwNzQ3OTc2ZTQ4NDZiNDggPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42ODk1NzQzLC03OS4zODMxNTk5MDAwMDAwMV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9hNWY2N2YyNDI4N2Q0ZTk2ODgyMTY0M2M2ZTM0ZTNlZiA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF8xMjgyYzcwNjI4YzI0OWE4OTRmMTdiMzgyY2ViNzJlYiA9ICQoJzxkaXYgaWQ9Imh0bWxfMTI4MmM3MDYyOGMyNDlhODk0ZjE3YjM4MmNlYjcyZWIiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPk1vb3JlIFBhcmssIFN1bW1lcmhpbGwgRWFzdCwgQ2VudHJhbCBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF9hNWY2N2YyNDI4N2Q0ZTk2ODgyMTY0M2M2ZTM0ZTNlZi5zZXRDb250ZW50KGh0bWxfMTI4MmM3MDYyOGMyNDlhODk0ZjE3YjM4MmNlYjcyZWIpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfZmY0NWRmMDQ5Zjk0NGNmNGEwNzQ3OTc2ZTQ4NDZiNDguYmluZFBvcHVwKHBvcHVwX2E1ZjY3ZjI0Mjg3ZDRlOTY4ODIxNjQzYzZlMzRlM2VmKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzQxNmQ1ZTY2YmY5YTRkYjJiOTRlMDczM2Y5Mjk5M2Y0ID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjUzMjA1NywtNzkuNDAwMDQ5M10sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF84NzI1MmE4M2FiZjk0NDk0YWU0MTYyOWVkNGYzNzAxNCA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9jMGE5ODlmMjVhN2U0YWQ5ODRkZWFiOGUzYWNjZDdkOCA9ICQoJzxkaXYgaWQ9Imh0bWxfYzBhOTg5ZjI1YTdlNGFkOTg0ZGVhYjhlM2FjY2Q3ZDgiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPktlbnNpbmd0b24gTWFya2V0LCBDaGluYXRvd24sIEdyYW5nZSBQYXJrLCBEb3dudG93biBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF84NzI1MmE4M2FiZjk0NDk0YWU0MTYyOWVkNGYzNzAxNC5zZXRDb250ZW50KGh0bWxfYzBhOTg5ZjI1YTdlNGFkOTg0ZGVhYjhlM2FjY2Q3ZDgpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfNDE2ZDVlNjZiZjlhNGRiMmI5NGUwNzMzZjkyOTkzZjQuYmluZFBvcHVwKHBvcHVwXzg3MjUyYTgzYWJmOTQ0OTRhZTQxNjI5ZWQ0ZjM3MDE0KTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyX2E3NDFlODY4NDgzMzQ4MjQ5NTAyZDFlNGY5MjMxMTA3ID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjg2NDEyMjk5OTk5OTksLTc5LjQwMDA0OTNdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiYmx1ZSIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMzMTg2Y2MiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfNDdkZTA4OGQ2YTJkNGVlMGIwOTNkN2FhZTg4ZjcxYWEgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfYjE0M2MyZTQ2ZWU3NDI4Zjk5OTA4NDU5OTk5OWY1NzIgPSAkKCc8ZGl2IGlkPSJodG1sX2IxNDNjMmU0NmVlNzQyOGY5OTkwODQ1OTk5OTlmNTcyIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5TdW1tZXJoaWxsIFdlc3QsIFJhdGhuZWxseSwgU291dGggSGlsbCwgRm9yZXN0IEhpbGwgU0UsIERlZXIgUGFyaywgQ2VudHJhbCBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF80N2RlMDg4ZDZhMmQ0ZWUwYjA5M2Q3YWFlODhmNzFhYS5zZXRDb250ZW50KGh0bWxfYjE0M2MyZTQ2ZWU3NDI4Zjk5OTA4NDU5OTk5OWY1NzIpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfYTc0MWU4Njg0ODMzNDgyNDk1MDJkMWU0ZjkyMzExMDcuYmluZFBvcHVwKHBvcHVwXzQ3ZGUwODhkNmEyZDRlZTBiMDkzZDdhYWU4OGY3MWFhKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyX2I5NGFhOTg1MTJiMjQwOGE4YWJiOTMxYjdjMTQzYTFkID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjI4OTQ2NywtNzkuMzk0NDE5OV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF8zOGFhMmRiNDM4MTA0ZjQ3OWY2NWE2NTU3ZGM3MzE2MyA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9jMGQ3NWY5OTcyMjQ0ZTJlYmQyOTBiNTE1N2I5YjdhYyA9ICQoJzxkaXYgaWQ9Imh0bWxfYzBkNzVmOTk3MjI0NGUyZWJkMjkwYjUxNTdiOWI3YWMiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPkNOIFRvd2VyLCBLaW5nIGFuZCBTcGFkaW5hLCBSYWlsd2F5IExhbmRzLCBIYXJib3VyZnJvbnQgV2VzdCwgQmF0aHVyc3QgUXVheSwgU291dGggTmlhZ2FyYSwgSXNsYW5kIGFpcnBvcnQsIERvd250b3duIFRvcm9udG88L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwXzM4YWEyZGI0MzgxMDRmNDc5ZjY1YTY1NTdkYzczMTYzLnNldENvbnRlbnQoaHRtbF9jMGQ3NWY5OTcyMjQ0ZTJlYmQyOTBiNTE1N2I5YjdhYyk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl9iOTRhYTk4NTEyYjI0MDhhOGFiYjkzMWI3YzE0M2ExZC5iaW5kUG9wdXAocG9wdXBfMzhhYTJkYjQzODEwNGY0NzlmNjVhNjU1N2RjNzMxNjMpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfMmJhY2U5Njg2MjEyNDZlOWIyOWQ2MmQyNjc5YTg4MzIgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42Nzk1NjI2LC03OS4zNzc1Mjk0MDAwMDAwMV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9hMjgxZDYzYTI2OWY0MTZhOTg4NzMzNjZiMjc3MzZjNyA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9kNTVhMTljNjhkYzU0MmM1YTI4ZDc1ZTUwNWE5MGFkMiA9ICQoJzxkaXYgaWQ9Imh0bWxfZDU1YTE5YzY4ZGM1NDJjNWEyOGQ3NWU1MDVhOTBhZDIiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPlJvc2VkYWxlLCBEb3dudG93biBUb3JvbnRvPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF9hMjgxZDYzYTI2OWY0MTZhOTg4NzMzNjZiMjc3MzZjNy5zZXRDb250ZW50KGh0bWxfZDU1YTE5YzY4ZGM1NDJjNWEyOGQ3NWU1MDVhOTBhZDIpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfMmJhY2U5Njg2MjEyNDZlOWIyOWQ2MmQyNjc5YTg4MzIuYmluZFBvcHVwKHBvcHVwX2EyODFkNjNhMjY5ZjQxNmE5ODg3MzM2NmIyNzczNmM3KTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyX2EyNDRhOTExN2UxMDRmY2U5NjM1NzhiODE3Y2RiNjAzID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjQ2NDM1MiwtNzkuMzc0ODQ1OTk5OTk5OTldLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiYmx1ZSIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMzMTg2Y2MiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfM2M5MGVlNmZkMzAwNGI2MDg4YTEyMDJjZWM0NjkyMDggPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfODBjMDdhNDczMDI0NDMzNWE4Nzc5OWQxMDRiZmZkMTggPSAkKCc8ZGl2IGlkPSJodG1sXzgwYzA3YTQ3MzAyNDQzMzVhODc3OTlkMTA0YmZmZDE4IiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5TdG4gQSBQTyBCb3hlcywgRG93bnRvd24gVG9yb250bzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfM2M5MGVlNmZkMzAwNGI2MDg4YTEyMDJjZWM0NjkyMDguc2V0Q29udGVudChodG1sXzgwYzA3YTQ3MzAyNDQzMzVhODc3OTlkMTA0YmZmZDE4KTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyX2EyNDRhOTExN2UxMDRmY2U5NjM1NzhiODE3Y2RiNjAzLmJpbmRQb3B1cChwb3B1cF8zYzkwZWU2ZmQzMDA0YjYwODhhMTIwMmNlYzQ2OTIwOCk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl84YTc2YmI2MzA2ZGM0ODZiYjkyMDAyN2YyY2VhNjQ2ZiA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY2Nzk2NywtNzkuMzY3Njc1M10sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICJibHVlIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzMxODZjYyIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82YmVjZjE5MWZiNjU0MjRhOThjNDNiOTk2Y2M5MDMxYSk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9kZDY2MjMyZmY1NWQ0YTlkYTVlYjRjYjYyMmQ4MjY2MiA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9mYjk4YTYyNGMwNmE0MjE3ODc1NmQ3Y2MyNDg4MDQ5YSA9ICQoJzxkaXYgaWQ9Imh0bWxfZmI5OGE2MjRjMDZhNDIxNzg3NTZkN2NjMjQ4ODA0OWEiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPlN0LiBKYW1lcyBUb3duLCBDYWJiYWdldG93biwgRG93bnRvd24gVG9yb250bzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfZGQ2NjIzMmZmNTVkNGE5ZGE1ZWI0Y2I2MjJkODI2NjIuc2V0Q29udGVudChodG1sX2ZiOThhNjI0YzA2YTQyMTc4NzU2ZDdjYzI0ODgwNDlhKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzhhNzZiYjYzMDZkYzQ4NmJiOTIwMDI3ZjJjZWE2NDZmLmJpbmRQb3B1cChwb3B1cF9kZDY2MjMyZmY1NWQ0YTlkYTVlYjRjYjYyMmQ4MjY2Mik7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl82MmE2NDhjNmViZGI0ZDUwYTAzOWRhMTExYmFmNjI2YiA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY0ODQyOTIsLTc5LjM4MjI4MDJdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiYmx1ZSIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMzMTg2Y2MiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfZGI4ZTMwNmY5YTBhNGUxZWJjMjYwMDNjMmJiOWIyNjYgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfMWI5YjM5MTUzMjY4NDUwNGJlNDk0MzRmYWI5OGZmNzcgPSAkKCc8ZGl2IGlkPSJodG1sXzFiOWIzOTE1MzI2ODQ1MDRiZTQ5NDM0ZmFiOThmZjc3IiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5GaXJzdCBDYW5hZGlhbiBQbGFjZSwgVW5kZXJncm91bmQgY2l0eSwgRG93bnRvd24gVG9yb250bzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfZGI4ZTMwNmY5YTBhNGUxZWJjMjYwMDNjMmJiOWIyNjYuc2V0Q29udGVudChodG1sXzFiOWIzOTE1MzI2ODQ1MDRiZTQ5NDM0ZmFiOThmZjc3KTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzYyYTY0OGM2ZWJkYjRkNTBhMDM5ZGExMTFiYWY2MjZiLmJpbmRQb3B1cChwb3B1cF9kYjhlMzA2ZjlhMGE0ZTFlYmMyNjAwM2MyYmI5YjI2Nik7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl85Njc3M2Y2ZmI2ODg0ZTZlYjhiNDgxNmRkNTc4ZjdjZCA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY2NTg1OTksLTc5LjM4MzE1OTkwMDAwMDAxXSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogImJsdWUiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjMzE4NmNjIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzZiZWNmMTkxZmI2NTQyNGE5OGM0M2I5OTZjYzkwMzFhKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwX2Q1MWI1OTRlNTcyOTQ3MjJiODBiYmY2MDgzZDgxMmJlID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sX2I0ZDA1ZTE0Y2VmOTQ5MTU4ODAyMjhkNTFhZWE4YzUzID0gJCgnPGRpdiBpZD0iaHRtbF9iNGQwNWUxNGNlZjk0OTE1ODgwMjI4ZDUxYWVhOGM1MyIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+Q2h1cmNoIGFuZCBXZWxsZXNsZXksIERvd250b3duIFRvcm9udG88L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwX2Q1MWI1OTRlNTcyOTQ3MjJiODBiYmY2MDgzZDgxMmJlLnNldENvbnRlbnQoaHRtbF9iNGQwNWUxNGNlZjk0OTE1ODgwMjI4ZDUxYWVhOGM1Myk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl85Njc3M2Y2ZmI2ODg0ZTZlYjhiNDgxNmRkNTc4ZjdjZC5iaW5kUG9wdXAocG9wdXBfZDUxYjU5NGU1NzI5NDcyMmI4MGJiZjYwODNkODEyYmUpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfZGI0NjAzYmZhYmRmNDhlZGFkNjRmNzFmYTQwOTkwYzggPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42NjI3NDM5LC03OS4zMjE1NThdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiYmx1ZSIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMzMTg2Y2MiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNmJlY2YxOTFmYjY1NDI0YTk4YzQzYjk5NmNjOTAzMWEpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfODU3Nzc1ZDZhNDIzNDI1MWJiYWJhZTNhNjY3YTFlYTUgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfZGY5YjkwZjVhMDE4NDllN2JlYjNkODkxYmQ1NDI2OTQgPSAkKCc8ZGl2IGlkPSJodG1sX2RmOWI5MGY1YTAxODQ5ZTdiZWIzZDg5MWJkNTQyNjk0IiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5CdXNpbmVzcyByZXBseSBtYWlsIFByb2Nlc3NpbmcgQ2VudHJlLCBTb3V0aCBDZW50cmFsIExldHRlciBQcm9jZXNzaW5nIFBsYW50IFRvcm9udG8sIEVhc3QgVG9yb250bzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfODU3Nzc1ZDZhNDIzNDI1MWJiYWJhZTNhNjY3YTFlYTUuc2V0Q29udGVudChodG1sX2RmOWI5MGY1YTAxODQ5ZTdiZWIzZDg5MWJkNTQyNjk0KTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyX2RiNDYwM2JmYWJkZjQ4ZWRhZDY0ZjcxZmE0MDk5MGM4LmJpbmRQb3B1cChwb3B1cF84NTc3NzVkNmE0MjM0MjUxYmJhYmFlM2E2NjdhMWVhNSk7CgogICAgICAgICAgICAKICAgICAgICAKPC9zY3JpcHQ+ onload="this.contentDocument.open();this.contentDocument.write(atob(this.getAttribute('data-html')));this.contentDocument.close();" allowfullscreen webkitallowfullscreen mozallowfullscreen></iframe></div></div>




```python
k=5
toronto_clustering = df4.drop(['Postal Code','Borough','Neighbourhood'],1)
kmeans = KMeans(n_clusters = k,random_state=0).fit(toronto_clustering)
kmeans.labels_
df4.insert(0, 'Cluster Labels', kmeans.labels_)
```


```python
df4
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Cluster Labels</th>
      <th>Postal Code</th>
      <th>Borough</th>
      <th>Neighbourhood</th>
      <th>Latitude</th>
      <th>Longitude</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>M5A</td>
      <td>Downtown Toronto</td>
      <td>Regent Park, Harbourfront</td>
      <td>43.654260</td>
      <td>-79.360636</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>M7A</td>
      <td>Downtown Toronto</td>
      <td>Queen's Park, Ontario Provincial Government</td>
      <td>43.662301</td>
      <td>-79.389494</td>
    </tr>
    <tr>
      <th>9</th>
      <td>0</td>
      <td>M5B</td>
      <td>Downtown Toronto</td>
      <td>Garden District, Ryerson</td>
      <td>43.657162</td>
      <td>-79.378937</td>
    </tr>
    <tr>
      <th>15</th>
      <td>0</td>
      <td>M5C</td>
      <td>Downtown Toronto</td>
      <td>St. James Town</td>
      <td>43.651494</td>
      <td>-79.375418</td>
    </tr>
    <tr>
      <th>19</th>
      <td>4</td>
      <td>M4E</td>
      <td>East Toronto</td>
      <td>The Beaches</td>
      <td>43.676357</td>
      <td>-79.293031</td>
    </tr>
    <tr>
      <th>20</th>
      <td>0</td>
      <td>M5E</td>
      <td>Downtown Toronto</td>
      <td>Berczy Park</td>
      <td>43.644771</td>
      <td>-79.373306</td>
    </tr>
    <tr>
      <th>24</th>
      <td>0</td>
      <td>M5G</td>
      <td>Downtown Toronto</td>
      <td>Central Bay Street</td>
      <td>43.657952</td>
      <td>-79.387383</td>
    </tr>
    <tr>
      <th>25</th>
      <td>3</td>
      <td>M6G</td>
      <td>Downtown Toronto</td>
      <td>Christie</td>
      <td>43.669542</td>
      <td>-79.422564</td>
    </tr>
    <tr>
      <th>30</th>
      <td>0</td>
      <td>M5H</td>
      <td>Downtown Toronto</td>
      <td>Richmond, Adelaide, King</td>
      <td>43.650571</td>
      <td>-79.384568</td>
    </tr>
    <tr>
      <th>31</th>
      <td>1</td>
      <td>M6H</td>
      <td>West Toronto</td>
      <td>Dufferin, Dovercourt Village</td>
      <td>43.669005</td>
      <td>-79.442259</td>
    </tr>
    <tr>
      <th>36</th>
      <td>0</td>
      <td>M5J</td>
      <td>Downtown Toronto</td>
      <td>Harbourfront East, Union Station, Toronto Islands</td>
      <td>43.640816</td>
      <td>-79.381752</td>
    </tr>
    <tr>
      <th>37</th>
      <td>3</td>
      <td>M6J</td>
      <td>West Toronto</td>
      <td>Little Portugal, Trinity</td>
      <td>43.647927</td>
      <td>-79.419750</td>
    </tr>
    <tr>
      <th>41</th>
      <td>4</td>
      <td>M4K</td>
      <td>East Toronto</td>
      <td>The Danforth West, Riverdale</td>
      <td>43.679557</td>
      <td>-79.352188</td>
    </tr>
    <tr>
      <th>42</th>
      <td>0</td>
      <td>M5K</td>
      <td>Downtown Toronto</td>
      <td>Toronto Dominion Centre, Design Exchange</td>
      <td>43.647177</td>
      <td>-79.381576</td>
    </tr>
    <tr>
      <th>43</th>
      <td>3</td>
      <td>M6K</td>
      <td>West Toronto</td>
      <td>Brockton, Parkdale Village, Exhibition Place</td>
      <td>43.636847</td>
      <td>-79.428191</td>
    </tr>
    <tr>
      <th>47</th>
      <td>4</td>
      <td>M4L</td>
      <td>East Toronto</td>
      <td>India Bazaar, The Beaches West</td>
      <td>43.668999</td>
      <td>-79.315572</td>
    </tr>
    <tr>
      <th>48</th>
      <td>0</td>
      <td>M5L</td>
      <td>Downtown Toronto</td>
      <td>Commerce Court, Victoria Hotel</td>
      <td>43.648198</td>
      <td>-79.379817</td>
    </tr>
    <tr>
      <th>54</th>
      <td>4</td>
      <td>M4M</td>
      <td>East Toronto</td>
      <td>Studio District</td>
      <td>43.659526</td>
      <td>-79.340923</td>
    </tr>
    <tr>
      <th>61</th>
      <td>2</td>
      <td>M4N</td>
      <td>Central Toronto</td>
      <td>Lawrence Park</td>
      <td>43.728020</td>
      <td>-79.388790</td>
    </tr>
    <tr>
      <th>62</th>
      <td>2</td>
      <td>M5N</td>
      <td>Central Toronto</td>
      <td>Roselawn</td>
      <td>43.711695</td>
      <td>-79.416936</td>
    </tr>
    <tr>
      <th>67</th>
      <td>2</td>
      <td>M4P</td>
      <td>Central Toronto</td>
      <td>Davisville North</td>
      <td>43.712751</td>
      <td>-79.390197</td>
    </tr>
    <tr>
      <th>68</th>
      <td>2</td>
      <td>M5P</td>
      <td>Central Toronto</td>
      <td>Forest Hill North &amp; West, Forest Hill Road Park</td>
      <td>43.696948</td>
      <td>-79.411307</td>
    </tr>
    <tr>
      <th>69</th>
      <td>1</td>
      <td>M6P</td>
      <td>West Toronto</td>
      <td>High Park, The Junction South</td>
      <td>43.661608</td>
      <td>-79.464763</td>
    </tr>
    <tr>
      <th>73</th>
      <td>2</td>
      <td>M4R</td>
      <td>Central Toronto</td>
      <td>North Toronto West, Lawrence Park</td>
      <td>43.715383</td>
      <td>-79.405678</td>
    </tr>
    <tr>
      <th>74</th>
      <td>3</td>
      <td>M5R</td>
      <td>Central Toronto</td>
      <td>The Annex, North Midtown, Yorkville</td>
      <td>43.672710</td>
      <td>-79.405678</td>
    </tr>
    <tr>
      <th>75</th>
      <td>1</td>
      <td>M6R</td>
      <td>West Toronto</td>
      <td>Parkdale, Roncesvalles</td>
      <td>43.648960</td>
      <td>-79.456325</td>
    </tr>
    <tr>
      <th>79</th>
      <td>2</td>
      <td>M4S</td>
      <td>Central Toronto</td>
      <td>Davisville</td>
      <td>43.704324</td>
      <td>-79.388790</td>
    </tr>
    <tr>
      <th>80</th>
      <td>3</td>
      <td>M5S</td>
      <td>Downtown Toronto</td>
      <td>University of Toronto, Harbord</td>
      <td>43.662696</td>
      <td>-79.400049</td>
    </tr>
    <tr>
      <th>81</th>
      <td>1</td>
      <td>M6S</td>
      <td>West Toronto</td>
      <td>Runnymede, Swansea</td>
      <td>43.651571</td>
      <td>-79.484450</td>
    </tr>
    <tr>
      <th>83</th>
      <td>2</td>
      <td>M4T</td>
      <td>Central Toronto</td>
      <td>Moore Park, Summerhill East</td>
      <td>43.689574</td>
      <td>-79.383160</td>
    </tr>
    <tr>
      <th>84</th>
      <td>3</td>
      <td>M5T</td>
      <td>Downtown Toronto</td>
      <td>Kensington Market, Chinatown, Grange Park</td>
      <td>43.653206</td>
      <td>-79.400049</td>
    </tr>
    <tr>
      <th>86</th>
      <td>2</td>
      <td>M4V</td>
      <td>Central Toronto</td>
      <td>Summerhill West, Rathnelly, South Hill, Forest...</td>
      <td>43.686412</td>
      <td>-79.400049</td>
    </tr>
    <tr>
      <th>87</th>
      <td>0</td>
      <td>M5V</td>
      <td>Downtown Toronto</td>
      <td>CN Tower, King and Spadina, Railway Lands, Har...</td>
      <td>43.628947</td>
      <td>-79.394420</td>
    </tr>
    <tr>
      <th>91</th>
      <td>0</td>
      <td>M4W</td>
      <td>Downtown Toronto</td>
      <td>Rosedale</td>
      <td>43.679563</td>
      <td>-79.377529</td>
    </tr>
    <tr>
      <th>92</th>
      <td>0</td>
      <td>M5W</td>
      <td>Downtown Toronto</td>
      <td>Stn A PO Boxes</td>
      <td>43.646435</td>
      <td>-79.374846</td>
    </tr>
    <tr>
      <th>96</th>
      <td>0</td>
      <td>M4X</td>
      <td>Downtown Toronto</td>
      <td>St. James Town, Cabbagetown</td>
      <td>43.667967</td>
      <td>-79.367675</td>
    </tr>
    <tr>
      <th>97</th>
      <td>0</td>
      <td>M5X</td>
      <td>Downtown Toronto</td>
      <td>First Canadian Place, Underground city</td>
      <td>43.648429</td>
      <td>-79.382280</td>
    </tr>
    <tr>
      <th>99</th>
      <td>0</td>
      <td>M4Y</td>
      <td>Downtown Toronto</td>
      <td>Church and Wellesley</td>
      <td>43.665860</td>
      <td>-79.383160</td>
    </tr>
    <tr>
      <th>100</th>
      <td>4</td>
      <td>M7Y</td>
      <td>East Toronto</td>
      <td>Business reply mail Processing Centre, South C...</td>
      <td>43.662744</td>
      <td>-79.321558</td>
    </tr>
  </tbody>
</table>
</div>




```python
# create map
map_clusters = folium.Map(location=[43.651070,-79.347015],zoom_start=10)

# set color scheme for the clusters
x = np.arange(k)
ys = [i + x + (i*x)**2 for i in range(k)]
colors_array = cm.rainbow(np.linspace(0, 1, len(ys)))
rainbow = [colors.rgb2hex(i) for i in colors_array]

# add markers to the map
markers_colors = []
for lat, lon, neighbourhood, cluster in zip(df4['Latitude'], df4['Longitude'], df4['Neighbourhood'], df4['Cluster Labels']):
    label = folium.Popup(' Cluster ' + str(cluster), parse_html=True)
    folium.CircleMarker(
        [lat, lon],
        radius=5,
        popup=label,
        color=rainbow[cluster-1],
        fill=True,
        fill_color=rainbow[cluster-1],
        fill_opacity=0.7).add_to(map_clusters)
       
map_clusters
```




<div style="width:100%;"><div style="position:relative;width:100%;height:0;padding-bottom:60%;"><span style="color:#565656">Make this Notebook Trusted to load map: File -> Trust Notebook</span><iframe src="about:blank" style="position:absolute;width:100%;height:100%;left:0;top:0;border:none !important;" data-html=PCFET0NUWVBFIGh0bWw+CjxoZWFkPiAgICAKICAgIDxtZXRhIGh0dHAtZXF1aXY9ImNvbnRlbnQtdHlwZSIgY29udGVudD0idGV4dC9odG1sOyBjaGFyc2V0PVVURi04IiAvPgogICAgPHNjcmlwdD5MX1BSRUZFUl9DQU5WQVMgPSBmYWxzZTsgTF9OT19UT1VDSCA9IGZhbHNlOyBMX0RJU0FCTEVfM0QgPSBmYWxzZTs8L3NjcmlwdD4KICAgIDxzY3JpcHQgc3JjPSJodHRwczovL2Nkbi5qc2RlbGl2ci5uZXQvbnBtL2xlYWZsZXRAMS4yLjAvZGlzdC9sZWFmbGV0LmpzIj48L3NjcmlwdD4KICAgIDxzY3JpcHQgc3JjPSJodHRwczovL2FqYXguZ29vZ2xlYXBpcy5jb20vYWpheC9saWJzL2pxdWVyeS8xLjExLjEvanF1ZXJ5Lm1pbi5qcyI+PC9zY3JpcHQ+CiAgICA8c2NyaXB0IHNyYz0iaHR0cHM6Ly9tYXhjZG4uYm9vdHN0cmFwY2RuLmNvbS9ib290c3RyYXAvMy4yLjAvanMvYm9vdHN0cmFwLm1pbi5qcyI+PC9zY3JpcHQ+CiAgICA8c2NyaXB0IHNyYz0iaHR0cHM6Ly9jZG5qcy5jbG91ZGZsYXJlLmNvbS9hamF4L2xpYnMvTGVhZmxldC5hd2Vzb21lLW1hcmtlcnMvMi4wLjIvbGVhZmxldC5hd2Vzb21lLW1hcmtlcnMuanMiPjwvc2NyaXB0PgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL2Nkbi5qc2RlbGl2ci5uZXQvbnBtL2xlYWZsZXRAMS4yLjAvZGlzdC9sZWFmbGV0LmNzcyIvPgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL21heGNkbi5ib290c3RyYXBjZG4uY29tL2Jvb3RzdHJhcC8zLjIuMC9jc3MvYm9vdHN0cmFwLm1pbi5jc3MiLz4KICAgIDxsaW5rIHJlbD0ic3R5bGVzaGVldCIgaHJlZj0iaHR0cHM6Ly9tYXhjZG4uYm9vdHN0cmFwY2RuLmNvbS9ib290c3RyYXAvMy4yLjAvY3NzL2Jvb3RzdHJhcC10aGVtZS5taW4uY3NzIi8+CiAgICA8bGluayByZWw9InN0eWxlc2hlZXQiIGhyZWY9Imh0dHBzOi8vbWF4Y2RuLmJvb3RzdHJhcGNkbi5jb20vZm9udC1hd2Vzb21lLzQuNi4zL2Nzcy9mb250LWF3ZXNvbWUubWluLmNzcyIvPgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL2NkbmpzLmNsb3VkZmxhcmUuY29tL2FqYXgvbGlicy9MZWFmbGV0LmF3ZXNvbWUtbWFya2Vycy8yLjAuMi9sZWFmbGV0LmF3ZXNvbWUtbWFya2Vycy5jc3MiLz4KICAgIDxsaW5rIHJlbD0ic3R5bGVzaGVldCIgaHJlZj0iaHR0cHM6Ly9yYXdnaXQuY29tL3B5dGhvbi12aXN1YWxpemF0aW9uL2ZvbGl1bS9tYXN0ZXIvZm9saXVtL3RlbXBsYXRlcy9sZWFmbGV0LmF3ZXNvbWUucm90YXRlLmNzcyIvPgogICAgPHN0eWxlPmh0bWwsIGJvZHkge3dpZHRoOiAxMDAlO2hlaWdodDogMTAwJTttYXJnaW46IDA7cGFkZGluZzogMDt9PC9zdHlsZT4KICAgIDxzdHlsZT4jbWFwIHtwb3NpdGlvbjphYnNvbHV0ZTt0b3A6MDtib3R0b206MDtyaWdodDowO2xlZnQ6MDt9PC9zdHlsZT4KICAgIAogICAgICAgICAgICA8c3R5bGU+ICNtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMgewogICAgICAgICAgICAgICAgcG9zaXRpb24gOiByZWxhdGl2ZTsKICAgICAgICAgICAgICAgIHdpZHRoIDogMTAwLjAlOwogICAgICAgICAgICAgICAgaGVpZ2h0OiAxMDAuMCU7CiAgICAgICAgICAgICAgICBsZWZ0OiAwLjAlOwogICAgICAgICAgICAgICAgdG9wOiAwLjAlOwogICAgICAgICAgICAgICAgfQogICAgICAgICAgICA8L3N0eWxlPgogICAgICAgIAo8L2hlYWQ+Cjxib2R5PiAgICAKICAgIAogICAgICAgICAgICA8ZGl2IGNsYXNzPSJmb2xpdW0tbWFwIiBpZD0ibWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjIiA+PC9kaXY+CiAgICAgICAgCjwvYm9keT4KPHNjcmlwdD4gICAgCiAgICAKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGJvdW5kcyA9IG51bGw7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgdmFyIG1hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYyA9IEwubWFwKAogICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgJ21hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYycsCiAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICB7Y2VudGVyOiBbNDMuNjUxMDcsLTc5LjM0NzAxNV0sCiAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICB6b29tOiAxMCwKICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgIG1heEJvdW5kczogYm91bmRzLAogICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgbGF5ZXJzOiBbXSwKICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgIHdvcmxkQ29weUp1bXA6IGZhbHNlLAogICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgY3JzOiBMLkNSUy5FUFNHMzg1NwogICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICB9KTsKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHRpbGVfbGF5ZXJfODg5YTg0MjI5OTczNDVkMGIzMjI4YmUwMTE2MDE3MGYgPSBMLnRpbGVMYXllcigKICAgICAgICAgICAgICAgICdodHRwczovL3tzfS50aWxlLm9wZW5zdHJlZXRtYXAub3JnL3t6fS97eH0ve3l9LnBuZycsCiAgICAgICAgICAgICAgICB7CiAgImF0dHJpYnV0aW9uIjogbnVsbCwKICAiZGV0ZWN0UmV0aW5hIjogZmFsc2UsCiAgIm1heFpvb20iOiAxOCwKICAibWluWm9vbSI6IDEsCiAgIm5vV3JhcCI6IGZhbHNlLAogICJzdWJkb21haW5zIjogImFiYyIKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzk5MDQ0OWNlMDQ3NTRhOWNhZGE2OGRiYjIzNjg0NzNiID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjU0MjU5OSwtNzkuMzYwNjM1OV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICIjZmYwMDAwIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiI2ZmMDAwMCIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYyk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9jMjc0ZGQyZjk2OTA0OTFhYTFjOWFiYTU0MjJkZWNiMSA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF82YTZhMzBmYTg4M2Q0NjRhODJhNmQ5ZjQxMThlNGVjZSA9ICQoJzxkaXYgaWQ9Imh0bWxfNmE2YTMwZmE4ODNkNDY0YTgyYTZkOWY0MTE4ZTRlY2UiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPiBDbHVzdGVyIDA8L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwX2MyNzRkZDJmOTY5MDQ5MWFhMWM5YWJhNTQyMmRlY2IxLnNldENvbnRlbnQoaHRtbF82YTZhMzBmYTg4M2Q0NjRhODJhNmQ5ZjQxMThlNGVjZSk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl85OTA0NDljZTA0NzU0YTljYWRhNjhkYmIyMzY4NDczYi5iaW5kUG9wdXAocG9wdXBfYzI3NGRkMmY5NjkwNDkxYWExYzlhYmE1NDIyZGVjYjEpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfNGI1NzNhYzMyNjVjNGNmMWE4YWEwMDUzYzFmYjUwZGYgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42NjIzMDE1LC03OS4zODk0OTM4XSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiNmZjAwMDAiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjZmYwMDAwIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwX2U3YjE1ZmU4Zjk0ODRjZDVhMDkwMWFjODZjOTM3ZTI0ID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sX2FmYjdjNWFlM2Y5NTQ3ZTNiNTYyZjA1NTNlODYzZWVmID0gJCgnPGRpdiBpZD0iaHRtbF9hZmI3YzVhZTNmOTU0N2UzYjU2MmYwNTUzZTg2M2VlZiIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgMDwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfZTdiMTVmZThmOTQ4NGNkNWEwOTAxYWM4NmM5MzdlMjQuc2V0Q29udGVudChodG1sX2FmYjdjNWFlM2Y5NTQ3ZTNiNTYyZjA1NTNlODYzZWVmKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzRiNTczYWMzMjY1YzRjZjFhOGFhMDA1M2MxZmI1MGRmLmJpbmRQb3B1cChwb3B1cF9lN2IxNWZlOGY5NDg0Y2Q1YTA5MDFhYzg2YzkzN2UyNCk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl8wMjNhNjZkN2Q2NWE0YWE4ODVlNjVmNzcxYWViM2YzMiA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY1NzE2MTgsLTc5LjM3ODkzNzA5OTk5OTk5XSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiNmZjAwMDAiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjZmYwMDAwIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzVlNzk4YTQyNzI1MzRiN2Y5OWRlODgyNmJlYWY2MmI0ID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzQ2YTY0NDI2NjI0ZjQ1ZDZhYTM4ZmY4MGEwYzkwZTdmID0gJCgnPGRpdiBpZD0iaHRtbF80NmE2NDQyNjYyNGY0NWQ2YWEzOGZmODBhMGM5MGU3ZiIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgMDwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfNWU3OThhNDI3MjUzNGI3Zjk5ZGU4ODI2YmVhZjYyYjQuc2V0Q29udGVudChodG1sXzQ2YTY0NDI2NjI0ZjQ1ZDZhYTM4ZmY4MGEwYzkwZTdmKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzAyM2E2NmQ3ZDY1YTRhYTg4NWU2NWY3NzFhZWIzZjMyLmJpbmRQb3B1cChwb3B1cF81ZTc5OGE0MjcyNTM0YjdmOTlkZTg4MjZiZWFmNjJiNCk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl82YTU5ZTA5OTQ4MjU0NWQ4OTk3ZTFhOTkyMGM4NGNhYiA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY1MTQ5MzksLTc5LjM3NTQxNzldLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiI2ZmMDAwMCIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiNmZjAwMDAiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfMTI5MTczYWIxNWQ2NGM3Yjk3MTU2YWM4NDY4YzFlOGEgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfYWMwMTUxNTUxNTM0NGQ3ZWIyNTQ2MjQ3ZmI0MTMzZjYgPSAkKCc8ZGl2IGlkPSJodG1sX2FjMDE1MTU1MTUzNDRkN2ViMjU0NjI0N2ZiNDEzM2Y2IiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij4gQ2x1c3RlciAwPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF8xMjkxNzNhYjE1ZDY0YzdiOTcxNTZhYzg0NjhjMWU4YS5zZXRDb250ZW50KGh0bWxfYWMwMTUxNTUxNTM0NGQ3ZWIyNTQ2MjQ3ZmI0MTMzZjYpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfNmE1OWUwOTk0ODI1NDVkODk5N2UxYTk5MjBjODRjYWIuYmluZFBvcHVwKHBvcHVwXzEyOTE3M2FiMTVkNjRjN2I5NzE1NmFjODQ2OGMxZThhKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzRiMWJlNzQ5YzUyNjQ0NmE5ZDMxODcyNjdjODdiYmE3ID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjc2MzU3Mzk5OTk5OTksLTc5LjI5MzAzMTJdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiI2ZmYjM2MCIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiNmZmIzNjAiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfMmUyMDhhOTcwNWYyNGY4MGJjZDMwYTYwMTc0NTE4YWMgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfYTMyYmY1YmJiNzYwNDY1ODg5ZGMzNzMzMjA4MWVlZTMgPSAkKCc8ZGl2IGlkPSJodG1sX2EzMmJmNWJiYjc2MDQ2NTg4OWRjMzczMzIwODFlZWUzIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij4gQ2x1c3RlciA0PC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF8yZTIwOGE5NzA1ZjI0ZjgwYmNkMzBhNjAxNzQ1MThhYy5zZXRDb250ZW50KGh0bWxfYTMyYmY1YmJiNzYwNDY1ODg5ZGMzNzMzMjA4MWVlZTMpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfNGIxYmU3NDljNTI2NDQ2YTlkMzE4NzI2N2M4N2JiYTcuYmluZFBvcHVwKHBvcHVwXzJlMjA4YTk3MDVmMjRmODBiY2QzMGE2MDE3NDUxOGFjKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzY1MDYxY2JmZGQzYTRhOTE4YjI2Y2NhNmE2OTc1ZWUwID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjQ0NzcwNzk5OTk5OTk2LC03OS4zNzMzMDY0XSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiNmZjAwMDAiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjZmYwMDAwIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzkzZTZjZGIyZTkzNzQ1NDQ4NGZiNWFkNGU1MWMyZjg4ID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzQxMmY2NDMyMDdkNzQwNjU5YTM4NTVjODZmZWRkN2Y2ID0gJCgnPGRpdiBpZD0iaHRtbF80MTJmNjQzMjA3ZDc0MDY1OWEzODU1Yzg2ZmVkZDdmNiIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgMDwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfOTNlNmNkYjJlOTM3NDU0NDg0ZmI1YWQ0ZTUxYzJmODguc2V0Q29udGVudChodG1sXzQxMmY2NDMyMDdkNzQwNjU5YTM4NTVjODZmZWRkN2Y2KTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzY1MDYxY2JmZGQzYTRhOTE4YjI2Y2NhNmE2OTc1ZWUwLmJpbmRQb3B1cChwb3B1cF85M2U2Y2RiMmU5Mzc0NTQ0ODRmYjVhZDRlNTFjMmY4OCk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9iMzIwNjU5NTYyYTc0OWI2YjFiZjE5NzIwMTdjMThiMyA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY1Nzk1MjQsLTc5LjM4NzM4MjZdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiI2ZmMDAwMCIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiNmZjAwMDAiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfOWEwN2U3YmFhYzIzNGVmMmIzN2JkM2IwMDQxOTY1Y2MgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfMDljOGE3ZmZlNWYxNGNhZjllNjEwNGRiY2Q4YWVkYWIgPSAkKCc8ZGl2IGlkPSJodG1sXzA5YzhhN2ZmZTVmMTRjYWY5ZTYxMDRkYmNkOGFlZGFiIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij4gQ2x1c3RlciAwPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF85YTA3ZTdiYWFjMjM0ZWYyYjM3YmQzYjAwNDE5NjVjYy5zZXRDb250ZW50KGh0bWxfMDljOGE3ZmZlNWYxNGNhZjllNjEwNGRiY2Q4YWVkYWIpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfYjMyMDY1OTU2MmE3NDliNmIxYmYxOTcyMDE3YzE4YjMuYmluZFBvcHVwKHBvcHVwXzlhMDdlN2JhYWMyMzRlZjJiMzdiZDNiMDA0MTk2NWNjKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzhhN2JkYWZiNWFlYjQ5ZDhhZGFkNWYxNzVmNzBlMTY5ID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjY5NTQyLC03OS40MjI1NjM3XSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiM4MGZmYjQiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjODBmZmI0IiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzliZjM4YzEyNTk0ZjRiMmZhM2QyYmM3MjMzMDIxYzZmID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzc2ZGU0MTNkZjU0MDQ3MTU4ODYxNzMyYzA1YjE0MjhiID0gJCgnPGRpdiBpZD0iaHRtbF83NmRlNDEzZGY1NDA0NzE1ODg2MTczMmMwNWIxNDI4YiIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgMzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfOWJmMzhjMTI1OTRmNGIyZmEzZDJiYzcyMzMwMjFjNmYuc2V0Q29udGVudChodG1sXzc2ZGU0MTNkZjU0MDQ3MTU4ODYxNzMyYzA1YjE0MjhiKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzhhN2JkYWZiNWFlYjQ5ZDhhZGFkNWYxNzVmNzBlMTY5LmJpbmRQb3B1cChwb3B1cF85YmYzOGMxMjU5NGY0YjJmYTNkMmJjNzIzMzAyMWM2Zik7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9kOTRiYmVmMzY0YmI0MTdiYTdiNDc5ZjQwMDRhZTE3NCA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY1MDU3MTIwMDAwMDAxLC03OS4zODQ1Njc1XSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiNmZjAwMDAiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjZmYwMDAwIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzNmMWI4ZTVlYzI4MjQ2M2ZhY2NjNTA5N2E2NDI3MTFmID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sX2Q2NGNkYTBlZDQ4MjQ4YjViNjg0YjgxYmI1MTY1YjM0ID0gJCgnPGRpdiBpZD0iaHRtbF9kNjRjZGEwZWQ0ODI0OGI1YjY4NGI4MWJiNTE2NWIzNCIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgMDwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfM2YxYjhlNWVjMjgyNDYzZmFjY2M1MDk3YTY0MjcxMWYuc2V0Q29udGVudChodG1sX2Q2NGNkYTBlZDQ4MjQ4YjViNjg0YjgxYmI1MTY1YjM0KTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyX2Q5NGJiZWYzNjRiYjQxN2JhN2I0NzlmNDAwNGFlMTc0LmJpbmRQb3B1cChwb3B1cF8zZjFiOGU1ZWMyODI0NjNmYWNjYzUwOTdhNjQyNzExZik7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl8wZWFiZjIxMTdmNTY0MjQ1OGEwOGU0YTI1NDJiNjk3NSA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY2OTAwNTEwMDAwMDAxLC03OS40NDIyNTkzXSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiM4MDAwZmYiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjODAwMGZmIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzQwODkzMGNmYjQyNTQzNGI4ZTk0OTAwNmNmNDhmMDIyID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sX2Y4OWI4NGRhM2VlOTQyYzA4ZDBkZjRiNWI2OGM1NzMzID0gJCgnPGRpdiBpZD0iaHRtbF9mODliODRkYTNlZTk0MmMwOGQwZGY0YjViNjhjNTczMyIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgMTwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfNDA4OTMwY2ZiNDI1NDM0YjhlOTQ5MDA2Y2Y0OGYwMjIuc2V0Q29udGVudChodG1sX2Y4OWI4NGRhM2VlOTQyYzA4ZDBkZjRiNWI2OGM1NzMzKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzBlYWJmMjExN2Y1NjQyNDU4YTA4ZTRhMjU0MmI2OTc1LmJpbmRQb3B1cChwb3B1cF80MDg5MzBjZmI0MjU0MzRiOGU5NDkwMDZjZjQ4ZjAyMik7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9iODBmNDcwZDFkMmE0NmNhYjlmMGU5MmYxNDk0NzkwNCA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY0MDgxNTcsLTc5LjM4MTc1MjI5OTk5OTk5XSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiNmZjAwMDAiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjZmYwMDAwIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzM0MTBmZDE4ODYyYjRjYmI4MTExNGQxYThlZWZhMjEzID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzY1NGEzNTgxZjdhODRjOGZhYTg2Y2JiOTJmOTQxMGJmID0gJCgnPGRpdiBpZD0iaHRtbF82NTRhMzU4MWY3YTg0YzhmYWE4NmNiYjkyZjk0MTBiZiIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgMDwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfMzQxMGZkMTg4NjJiNGNiYjgxMTE0ZDFhOGVlZmEyMTMuc2V0Q29udGVudChodG1sXzY1NGEzNTgxZjdhODRjOGZhYTg2Y2JiOTJmOTQxMGJmKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyX2I4MGY0NzBkMWQyYTQ2Y2FiOWYwZTkyZjE0OTQ3OTA0LmJpbmRQb3B1cChwb3B1cF8zNDEwZmQxODg2MmI0Y2JiODExMTRkMWE4ZWVmYTIxMyk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9hMTM2YWJhMmVlZGY0MWYzYTQwZDBhZTQ0MDk3YzdiNCA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY0NzkyNjcwMDAwMDAwNiwtNzkuNDE5NzQ5N10sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICIjODBmZmI0IiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzgwZmZiNCIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYyk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9hMTcyMWYwZTBiNzY0NzE3YmQ5M2M4NjI1YzI4MTVjOCA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF84MTQ5M2E0ODdhZjA0ZTk2YTliN2YyNTY4NGEzM2ExMSA9ICQoJzxkaXYgaWQ9Imh0bWxfODE0OTNhNDg3YWYwNGU5NmE5YjdmMjU2ODRhMzNhMTEiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPiBDbHVzdGVyIDM8L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwX2ExNzIxZjBlMGI3NjQ3MTdiZDkzYzg2MjVjMjgxNWM4LnNldENvbnRlbnQoaHRtbF84MTQ5M2E0ODdhZjA0ZTk2YTliN2YyNTY4NGEzM2ExMSk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl9hMTM2YWJhMmVlZGY0MWYzYTQwZDBhZTQ0MDk3YzdiNC5iaW5kUG9wdXAocG9wdXBfYTE3MjFmMGUwYjc2NDcxN2JkOTNjODYyNWMyODE1YzgpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfMmZiMjg0OTY4ZGJlNDJlOGI4MmU1YmI0NzBjYWRjNGMgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42Nzk1NTcxLC03OS4zNTIxODhdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiI2ZmYjM2MCIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiNmZmIzNjAiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfNmEwZjJiNWQzNTVkNGU4Mjg2N2FjNGVhMGY3NWQ0YWYgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfMzQzZTZiYzZjMTk5NGFjYzlhMmVmMDEyMDE5ZjY1NDIgPSAkKCc8ZGl2IGlkPSJodG1sXzM0M2U2YmM2YzE5OTRhY2M5YTJlZjAxMjAxOWY2NTQyIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij4gQ2x1c3RlciA0PC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF82YTBmMmI1ZDM1NWQ0ZTgyODY3YWM0ZWEwZjc1ZDRhZi5zZXRDb250ZW50KGh0bWxfMzQzZTZiYzZjMTk5NGFjYzlhMmVmMDEyMDE5ZjY1NDIpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfMmZiMjg0OTY4ZGJlNDJlOGI4MmU1YmI0NzBjYWRjNGMuYmluZFBvcHVwKHBvcHVwXzZhMGYyYjVkMzU1ZDRlODI4NjdhYzRlYTBmNzVkNGFmKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzJhZGM2ZTU3Mjg4NzRhZmRhZDdhMjc2MDQ4NTE0ZTczID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjQ3MTc2OCwtNzkuMzgxNTc2NDAwMDAwMDFdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiI2ZmMDAwMCIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiNmZjAwMDAiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfZTRiMzhlZTU3YTI4NDIwZmI4NzMyMTMxZTBhYThiMTIgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfYzE4OTA1Y2ZjYTZjNDFlM2I1YmU5OTFiNWI1MmI3OGUgPSAkKCc8ZGl2IGlkPSJodG1sX2MxODkwNWNmY2E2YzQxZTNiNWJlOTkxYjViNTJiNzhlIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij4gQ2x1c3RlciAwPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF9lNGIzOGVlNTdhMjg0MjBmYjg3MzIxMzFlMGFhOGIxMi5zZXRDb250ZW50KGh0bWxfYzE4OTA1Y2ZjYTZjNDFlM2I1YmU5OTFiNWI1MmI3OGUpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfMmFkYzZlNTcyODg3NGFmZGFkN2EyNzYwNDg1MTRlNzMuYmluZFBvcHVwKHBvcHVwX2U0YjM4ZWU1N2EyODQyMGZiODczMjEzMWUwYWE4YjEyKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyX2RhZTMxMjc2MTMzODQ1YjlhMWNlZTRmMzQwMTg5ZTBhID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjM2ODQ3MiwtNzkuNDI4MTkxNDAwMDAwMDJdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiIzgwZmZiNCIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiM4MGZmYjQiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfMmZmYTliOTg0NzZlNGU3NmE1ZTRmNzZjZGU4YjZjMDkgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfYTI2ZTEzZjllMWY5NGMwYzhjMTE0NTFmZDZiN2FjMjggPSAkKCc8ZGl2IGlkPSJodG1sX2EyNmUxM2Y5ZTFmOTRjMGM4YzExNDUxZmQ2YjdhYzI4IiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij4gQ2x1c3RlciAzPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF8yZmZhOWI5ODQ3NmU0ZTc2YTVlNGY3NmNkZThiNmMwOS5zZXRDb250ZW50KGh0bWxfYTI2ZTEzZjllMWY5NGMwYzhjMTE0NTFmZDZiN2FjMjgpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfZGFlMzEyNzYxMzM4NDViOWExY2VlNGYzNDAxODllMGEuYmluZFBvcHVwKHBvcHVwXzJmZmE5Yjk4NDc2ZTRlNzZhNWU0Zjc2Y2RlOGI2YzA5KTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyX2Y5NmQyMjFiMTczNDRlMzNhNDBhODczMGQxOTY0OGU1ID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjY4OTk4NSwtNzkuMzE1NTcxNTk5OTk5OThdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiI2ZmYjM2MCIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiNmZmIzNjAiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfMTM3NWE4ODI5NDNkNDc3OTkwZTdmZDAwZTMxN2Y2MzQgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfNWQzOGJhN2UzZWFhNDEzODg5ZGEzYzhiOGE0MWE0NjQgPSAkKCc8ZGl2IGlkPSJodG1sXzVkMzhiYTdlM2VhYTQxMzg4OWRhM2M4YjhhNDFhNDY0IiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij4gQ2x1c3RlciA0PC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF8xMzc1YTg4Mjk0M2Q0Nzc5OTBlN2ZkMDBlMzE3ZjYzNC5zZXRDb250ZW50KGh0bWxfNWQzOGJhN2UzZWFhNDEzODg5ZGEzYzhiOGE0MWE0NjQpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfZjk2ZDIyMWIxNzM0NGUzM2E0MGE4NzMwZDE5NjQ4ZTUuYmluZFBvcHVwKHBvcHVwXzEzNzVhODgyOTQzZDQ3Nzk5MGU3ZmQwMGUzMTdmNjM0KTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzc5MGRmZWFlZjljZjRlZmM5YjNlZTZiNDEwYThjMTg5ID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjQ4MTk4NSwtNzkuMzc5ODE2OTAwMDAwMDFdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiI2ZmMDAwMCIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiNmZjAwMDAiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfYTY3OTA0ZWJkOTFlNGZmMzgwYmQxZjczYTFlYjJiOWUgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfYjY5NTY3YWZjMGRhNDJhYmJjNGUwYmRhZDI0ODUxZjcgPSAkKCc8ZGl2IGlkPSJodG1sX2I2OTU2N2FmYzBkYTQyYWJiYzRlMGJkYWQyNDg1MWY3IiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij4gQ2x1c3RlciAwPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF9hNjc5MDRlYmQ5MWU0ZmYzODBiZDFmNzNhMWViMmI5ZS5zZXRDb250ZW50KGh0bWxfYjY5NTY3YWZjMGRhNDJhYmJjNGUwYmRhZDI0ODUxZjcpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfNzkwZGZlYWVmOWNmNGVmYzliM2VlNmI0MTBhOGMxODkuYmluZFBvcHVwKHBvcHVwX2E2NzkwNGViZDkxZTRmZjM4MGJkMWY3M2ExZWIyYjllKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzE0MjBkNmVkNWY3ZTQwYzU5N2I4ZDg2MzAzYzE3Y2Y2ID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjU5NTI1NSwtNzkuMzQwOTIzXSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiNmZmIzNjAiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjZmZiMzYwIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzlkYmUwYmQ3OTgxNjQyY2U5MTk3MmY1NzllMDI5N2I3ID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzhiODFmMmQ5ZjBhYjRlOThhZjgwMTZiOGIyMDYxZDg5ID0gJCgnPGRpdiBpZD0iaHRtbF84YjgxZjJkOWYwYWI0ZTk4YWY4MDE2YjhiMjA2MWQ4OSIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgNDwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfOWRiZTBiZDc5ODE2NDJjZTkxOTcyZjU3OWUwMjk3Yjcuc2V0Q29udGVudChodG1sXzhiODFmMmQ5ZjBhYjRlOThhZjgwMTZiOGIyMDYxZDg5KTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzE0MjBkNmVkNWY3ZTQwYzU5N2I4ZDg2MzAzYzE3Y2Y2LmJpbmRQb3B1cChwb3B1cF85ZGJlMGJkNzk4MTY0MmNlOTE5NzJmNTc5ZTAyOTdiNyk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9hZDE3MmU5OGJiNDA0YWNmYTdlNzI0YTMyMWFmMzViZCA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjcyODAyMDUsLTc5LjM4ODc5MDFdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiIzAwYjVlYiIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMwMGI1ZWIiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfMmI2MDMyYzI2NzgzNDJmNGJiMGNmNTNkOWY5ODhlODYgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfNzhmYzc4NmFmM2RmNDFlY2E2ZmFhZjZiY2QzMDBhNjggPSAkKCc8ZGl2IGlkPSJodG1sXzc4ZmM3ODZhZjNkZjQxZWNhNmZhYWY2YmNkMzAwYTY4IiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij4gQ2x1c3RlciAyPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF8yYjYwMzJjMjY3ODM0MmY0YmIwY2Y1M2Q5Zjk4OGU4Ni5zZXRDb250ZW50KGh0bWxfNzhmYzc4NmFmM2RmNDFlY2E2ZmFhZjZiY2QzMDBhNjgpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfYWQxNzJlOThiYjQwNGFjZmE3ZTcyNGEzMjFhZjM1YmQuYmluZFBvcHVwKHBvcHVwXzJiNjAzMmMyNjc4MzQyZjRiYjBjZjUzZDlmOTg4ZTg2KTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyX2QxYWMyODcwMWQ0NDRlYmNiM2E3ZTk3NmM2YjlmOTFlID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNzExNjk0OCwtNzkuNDE2OTM1NTk5OTk5OTldLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiIzAwYjVlYiIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMwMGI1ZWIiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfYjZiMTNhNmMxNjQ4NGMzMzkzN2NlMmMyZjdjZTFhOWYgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfOTFkM2Y2NTBkNjJmNGFiMWFiNGM1MDYyZDFkODBiYjAgPSAkKCc8ZGl2IGlkPSJodG1sXzkxZDNmNjUwZDYyZjRhYjFhYjRjNTA2MmQxZDgwYmIwIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij4gQ2x1c3RlciAyPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF9iNmIxM2E2YzE2NDg0YzMzOTM3Y2UyYzJmN2NlMWE5Zi5zZXRDb250ZW50KGh0bWxfOTFkM2Y2NTBkNjJmNGFiMWFiNGM1MDYyZDFkODBiYjApOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfZDFhYzI4NzAxZDQ0NGViY2IzYTdlOTc2YzZiOWY5MWUuYmluZFBvcHVwKHBvcHVwX2I2YjEzYTZjMTY0ODRjMzM5MzdjZTJjMmY3Y2UxYTlmKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzllYzY2ODU4MDZiOTRiMzBhYzRhMDYxYTllYjY0YzNlID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNzEyNzUxMSwtNzkuMzkwMTk3NV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICIjMDBiNWViIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzAwYjVlYiIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYyk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF81ODk5MWMzMzRjMTE0NTllYmQ3ODEzZTZhNzE5ZDA5YyA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9jOTY2NjY2MzhkNTI0YjE3ODg0NGVlYWMwMjcxNjQ1YSA9ICQoJzxkaXYgaWQ9Imh0bWxfYzk2NjY2NjM4ZDUyNGIxNzg4NDRlZWFjMDI3MTY0NWEiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPiBDbHVzdGVyIDI8L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwXzU4OTkxYzMzNGMxMTQ1OWViZDc4MTNlNmE3MTlkMDljLnNldENvbnRlbnQoaHRtbF9jOTY2NjY2MzhkNTI0YjE3ODg0NGVlYWMwMjcxNjQ1YSk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl85ZWM2Njg1ODA2Yjk0YjMwYWM0YTA2MWE5ZWI2NGMzZS5iaW5kUG9wdXAocG9wdXBfNTg5OTFjMzM0YzExNDU5ZWJkNzgxM2U2YTcxOWQwOWMpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfMTdjYjQ3MmQ0YzgzNDU3ZjgzMWIwNjNlMTI2YjAzMTIgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42OTY5NDc2LC03OS40MTEzMDcyMDAwMDAwMV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICIjMDBiNWViIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzAwYjVlYiIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYyk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF8zZTJmYTdlZDI2NGY0ZDI2OGE2M2M0MzkxYzMwYWU4MSA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF82ZDdiYWQzMjNmMmI0NDc3OWVjMjk1MmEyMTJmOWIxMSA9ICQoJzxkaXYgaWQ9Imh0bWxfNmQ3YmFkMzIzZjJiNDQ3NzllYzI5NTJhMjEyZjliMTEiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPiBDbHVzdGVyIDI8L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwXzNlMmZhN2VkMjY0ZjRkMjY4YTYzYzQzOTFjMzBhZTgxLnNldENvbnRlbnQoaHRtbF82ZDdiYWQzMjNmMmI0NDc3OWVjMjk1MmEyMTJmOWIxMSk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl8xN2NiNDcyZDRjODM0NTdmODMxYjA2M2UxMjZiMDMxMi5iaW5kUG9wdXAocG9wdXBfM2UyZmE3ZWQyNjRmNGQyNjhhNjNjNDM5MWMzMGFlODEpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfMDczNzA4ZjMzM2RkNGU3YzkxNjIwYjFiNGUxOWMxNzggPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42NjE2MDgzLC03OS40NjQ3NjMyOTk5OTk5OV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICIjODAwMGZmIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzgwMDBmZiIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYyk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF85OGMyNmIxZDU3MDM0MTk2OTg0MTFjYWM3ZmIwNTVjMyA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF8yMzVlNjA5ZDU2NjA0OWQ4YmM0N2RjY2JjNTY2YzNkOCA9ICQoJzxkaXYgaWQ9Imh0bWxfMjM1ZTYwOWQ1NjYwNDlkOGJjNDdkY2NiYzU2NmMzZDgiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPiBDbHVzdGVyIDE8L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwXzk4YzI2YjFkNTcwMzQxOTY5ODQxMWNhYzdmYjA1NWMzLnNldENvbnRlbnQoaHRtbF8yMzVlNjA5ZDU2NjA0OWQ4YmM0N2RjY2JjNTY2YzNkOCk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl8wNzM3MDhmMzMzZGQ0ZTdjOTE2MjBiMWI0ZTE5YzE3OC5iaW5kUG9wdXAocG9wdXBfOThjMjZiMWQ1NzAzNDE5Njk4NDExY2FjN2ZiMDU1YzMpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfMjdiODMzMzcyMjU5NDExMGJmNzYwMzRiMmM4YmM2MDAgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My43MTUzODM0LC03OS40MDU2Nzg0MDAwMDAwMV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICIjMDBiNWViIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzAwYjVlYiIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYyk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF81MGU0MmFlNmFlOGE0YTllYmE2NWIxZGQyZjljZGYyOSA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF8zYzZlNWZjMzUxMTg0YzU4ODBjZTIwNWQ2YzAwMGI4OCA9ICQoJzxkaXYgaWQ9Imh0bWxfM2M2ZTVmYzM1MTE4NGM1ODgwY2UyMDVkNmMwMDBiODgiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPiBDbHVzdGVyIDI8L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwXzUwZTQyYWU2YWU4YTRhOWViYTY1YjFkZDJmOWNkZjI5LnNldENvbnRlbnQoaHRtbF8zYzZlNWZjMzUxMTg0YzU4ODBjZTIwNWQ2YzAwMGI4OCk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl8yN2I4MzMzNzIyNTk0MTEwYmY3NjAzNGIyYzhiYzYwMC5iaW5kUG9wdXAocG9wdXBfNTBlNDJhZTZhZThhNGE5ZWJhNjViMWRkMmY5Y2RmMjkpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfZmRjZDhjYTdiMGY4NGU3ZGI5YzRiMDJmZmVjYTEwNmQgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42NzI3MDk3LC03OS40MDU2Nzg0MDAwMDAwMV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICIjODBmZmI0IiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzgwZmZiNCIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYyk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9lZWM5ZjMxZTQxMjk0MWMwOWRmMDM4MmNlZjRjMmEwNCA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF80MGMzMTE4OWExMDY0YTNhYjk2MWExZjYwOTZlNjAyYiA9ICQoJzxkaXYgaWQ9Imh0bWxfNDBjMzExODlhMTA2NGEzYWI5NjFhMWY2MDk2ZTYwMmIiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPiBDbHVzdGVyIDM8L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwX2VlYzlmMzFlNDEyOTQxYzA5ZGYwMzgyY2VmNGMyYTA0LnNldENvbnRlbnQoaHRtbF80MGMzMTE4OWExMDY0YTNhYjk2MWExZjYwOTZlNjAyYik7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl9mZGNkOGNhN2IwZjg0ZTdkYjljNGIwMmZmZWNhMTA2ZC5iaW5kUG9wdXAocG9wdXBfZWVjOWYzMWU0MTI5NDFjMDlkZjAzODJjZWY0YzJhMDQpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfM2FiMmFkM2JmYWRhNGFmZmFlMThlNDA5MGVkOGY3ZjcgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42NDg5NTk3LC03OS40NTYzMjVdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiIzgwMDBmZiIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiM4MDAwZmYiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfMGIxNjE1YmMzYjI3NGVhMTljODk0Y2NkY2Q4NDVlZTEgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfYmQwZjY0MDdiZjkyNDhkNzg4ZGQzMjI5ZjgzZjE0ZmYgPSAkKCc8ZGl2IGlkPSJodG1sX2JkMGY2NDA3YmY5MjQ4ZDc4OGRkMzIyOWY4M2YxNGZmIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij4gQ2x1c3RlciAxPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF8wYjE2MTViYzNiMjc0ZWExOWM4OTRjY2RjZDg0NWVlMS5zZXRDb250ZW50KGh0bWxfYmQwZjY0MDdiZjkyNDhkNzg4ZGQzMjI5ZjgzZjE0ZmYpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfM2FiMmFkM2JmYWRhNGFmZmFlMThlNDA5MGVkOGY3ZjcuYmluZFBvcHVwKHBvcHVwXzBiMTYxNWJjM2IyNzRlYTE5Yzg5NGNjZGNkODQ1ZWUxKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzI4NjRmMjA0ODU0NTRlOGE5ZThmYTEwODg3YWFhMDU3ID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNzA0MzI0NCwtNzkuMzg4NzkwMV0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICIjMDBiNWViIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzAwYjVlYiIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYyk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9lZTMwOGJkYmI1ZWY0ZDk1YTFhYzZjYzA0OTI5ZTRiMCA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9kMDcyZGIxOGM1ZGE0MmI4YjVlOTBiZDE1NDdmNDVhOCA9ICQoJzxkaXYgaWQ9Imh0bWxfZDA3MmRiMThjNWRhNDJiOGI1ZTkwYmQxNTQ3ZjQ1YTgiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPiBDbHVzdGVyIDI8L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwX2VlMzA4YmRiYjVlZjRkOTVhMWFjNmNjMDQ5MjllNGIwLnNldENvbnRlbnQoaHRtbF9kMDcyZGIxOGM1ZGE0MmI4YjVlOTBiZDE1NDdmNDVhOCk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl8yODY0ZjIwNDg1NDU0ZThhOWU4ZmExMDg4N2FhYTA1Ny5iaW5kUG9wdXAocG9wdXBfZWUzMDhiZGJiNWVmNGQ5NWExYWM2Y2MwNDkyOWU0YjApOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfNDkwZTgzNjI5OWY3NGM2ZmExNGVmYmZlNTc2OTZkODcgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42NjI2OTU2LC03OS40MDAwNDkzXSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiM4MGZmYjQiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjODBmZmI0IiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzVjZDlkNWI3ODJjZjQyMDk4OGZmZDhlYjczYWI2NGYzID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sX2ExY2MwOThlZjRlYjRiOTdhOTRkMTI1ZGZkZmU3MDI3ID0gJCgnPGRpdiBpZD0iaHRtbF9hMWNjMDk4ZWY0ZWI0Yjk3YTk0ZDEyNWRmZGZlNzAyNyIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgMzwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfNWNkOWQ1Yjc4MmNmNDIwOTg4ZmZkOGViNzNhYjY0ZjMuc2V0Q29udGVudChodG1sX2ExY2MwOThlZjRlYjRiOTdhOTRkMTI1ZGZkZmU3MDI3KTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzQ5MGU4MzYyOTlmNzRjNmZhMTRlZmJmZTU3Njk2ZDg3LmJpbmRQb3B1cChwb3B1cF81Y2Q5ZDViNzgyY2Y0MjA5ODhmZmQ4ZWI3M2FiNjRmMyk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9lNmFiNDU3MmJiOTQ0ZmZhYTg2MDU1NGY0NGI4ZDFhOSA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY1MTU3MDYsLTc5LjQ4NDQ0OTldLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiIzgwMDBmZiIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiM4MDAwZmYiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfODJlZjM4MDFjMjZlNDg3MTllZTM4MmUzNzQ5Y2NkNTggPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfYWYzYzA4MzM3ZDZlNGU4NTkzMTE5NTdkODhmMTI4OWIgPSAkKCc8ZGl2IGlkPSJodG1sX2FmM2MwODMzN2Q2ZTRlODU5MzExOTU3ZDg4ZjEyODliIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij4gQ2x1c3RlciAxPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF84MmVmMzgwMWMyNmU0ODcxOWVlMzgyZTM3NDljY2Q1OC5zZXRDb250ZW50KGh0bWxfYWYzYzA4MzM3ZDZlNGU4NTkzMTE5NTdkODhmMTI4OWIpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfZTZhYjQ1NzJiYjk0NGZmYWE4NjA1NTRmNDRiOGQxYTkuYmluZFBvcHVwKHBvcHVwXzgyZWYzODAxYzI2ZTQ4NzE5ZWUzODJlMzc0OWNjZDU4KTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzlkMWM0MGNiNGIzZDQ5YWI4NzRjYjU5YzBjZmE2ZjVlID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjg5NTc0MywtNzkuMzgzMTU5OTAwMDAwMDFdLAogICAgICAgICAgICAgICAgewogICJidWJibGluZ01vdXNlRXZlbnRzIjogdHJ1ZSwKICAiY29sb3IiOiAiIzAwYjVlYiIsCiAgImRhc2hBcnJheSI6IG51bGwsCiAgImRhc2hPZmZzZXQiOiBudWxsLAogICJmaWxsIjogdHJ1ZSwKICAiZmlsbENvbG9yIjogIiMwMGI1ZWIiLAogICJmaWxsT3BhY2l0eSI6IDAuNywKICAiZmlsbFJ1bGUiOiAiZXZlbm9kZCIsCiAgImxpbmVDYXAiOiAicm91bmQiLAogICJsaW5lSm9pbiI6ICJyb3VuZCIsCiAgIm9wYWNpdHkiOiAxLjAsCiAgInJhZGl1cyI6IDUsCiAgInN0cm9rZSI6IHRydWUsCiAgIndlaWdodCI6IDMKfQogICAgICAgICAgICAgICAgKS5hZGRUbyhtYXBfNjE2MTU3OWQ3MjY2NDQwODlkZmY2ZjRiMDczODI1MGMpOwogICAgICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgcG9wdXBfMDhkYTliYzdkMTZjNDhkNTkwMTM3NDNhODVlNDkxMWQgPSBMLnBvcHVwKHttYXhXaWR0aDogJzMwMCd9KTsKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGh0bWxfMzE0OGQyN2M1MmM5NDFjZWFlYjNlNzMwODc2OWM4ZmEgPSAkKCc8ZGl2IGlkPSJodG1sXzMxNDhkMjdjNTJjOTQxY2VhZWIzZTczMDg3NjljOGZhIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij4gQ2x1c3RlciAyPC9kaXY+JylbMF07CiAgICAgICAgICAgICAgICBwb3B1cF8wOGRhOWJjN2QxNmM0OGQ1OTAxMzc0M2E4NWU0OTExZC5zZXRDb250ZW50KGh0bWxfMzE0OGQyN2M1MmM5NDFjZWFlYjNlNzMwODc2OWM4ZmEpOwogICAgICAgICAgICAKCiAgICAgICAgICAgIGNpcmNsZV9tYXJrZXJfOWQxYzQwY2I0YjNkNDlhYjg3NGNiNTljMGNmYTZmNWUuYmluZFBvcHVwKHBvcHVwXzA4ZGE5YmM3ZDE2YzQ4ZDU5MDEzNzQzYTg1ZTQ5MTFkKTsKCiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBjaXJjbGVfbWFya2VyXzgzY2E5NTAzYjAzYjRjYjk4NWI3YjllN2YwYmQ5ODIyID0gTC5jaXJjbGVNYXJrZXIoCiAgICAgICAgICAgICAgICBbNDMuNjUzMjA1NywtNzkuNDAwMDQ5M10sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICIjODBmZmI0IiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzgwZmZiNCIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYyk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF8yYjM1NjU3YmZkMWU0NGM4OWEyYzdlMzQ0Nzk5OTZlZiA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9iYWQzM2UwYzc5MzM0YTFjODU4MDcyZTE1M2M3MGY0NSA9ICQoJzxkaXYgaWQ9Imh0bWxfYmFkMzNlMGM3OTMzNGExYzg1ODA3MmUxNTNjNzBmNDUiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPiBDbHVzdGVyIDM8L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwXzJiMzU2NTdiZmQxZTQ0Yzg5YTJjN2UzNDQ3OTk5NmVmLnNldENvbnRlbnQoaHRtbF9iYWQzM2UwYzc5MzM0YTFjODU4MDcyZTE1M2M3MGY0NSk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl84M2NhOTUwM2IwM2I0Y2I5ODViN2I5ZTdmMGJkOTgyMi5iaW5kUG9wdXAocG9wdXBfMmIzNTY1N2JmZDFlNDRjODlhMmM3ZTM0NDc5OTk2ZWYpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfZDYzYTY4MTY5MmE1NDgxY2IxMTQwZjI2ZmM3ZDIyNjkgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42ODY0MTIyOTk5OTk5OSwtNzkuNDAwMDQ5M10sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICIjMDBiNWViIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiIzAwYjVlYiIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYyk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF82NjI4OWI5NWIyZmY0YjM2OTc2NmUzODdmODM0YTNlYiA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9kMGVkOThmZWRhYWM0Njg0YWM4ZmQ3ZDYwYWNiNDJkNyA9ICQoJzxkaXYgaWQ9Imh0bWxfZDBlZDk4ZmVkYWFjNDY4NGFjOGZkN2Q2MGFjYjQyZDciIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPiBDbHVzdGVyIDI8L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwXzY2Mjg5Yjk1YjJmZjRiMzY5NzY2ZTM4N2Y4MzRhM2ViLnNldENvbnRlbnQoaHRtbF9kMGVkOThmZWRhYWM0Njg0YWM4ZmQ3ZDYwYWNiNDJkNyk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl9kNjNhNjgxNjkyYTU0ODFjYjExNDBmMjZmYzdkMjI2OS5iaW5kUG9wdXAocG9wdXBfNjYyODliOTViMmZmNGIzNjk3NjZlMzg3ZjgzNGEzZWIpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfZWIzNTdlOWE0MWQzNGExZWE0OGY4YmUxNDJlY2Q5ODkgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42Mjg5NDY3LC03OS4zOTQ0MTk5XSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiNmZjAwMDAiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjZmYwMDAwIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwX2UwYmM4YjYzMGNiNzQ4NjY4OGI1OWFiNzRkNGFjZDZmID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzU0YTI0NDg0NTExNDQxYzM5MTdhNmUwYTQ4NzNjOGY2ID0gJCgnPGRpdiBpZD0iaHRtbF81NGEyNDQ4NDUxMTQ0MWMzOTE3YTZlMGE0ODczYzhmNiIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgMDwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfZTBiYzhiNjMwY2I3NDg2Njg4YjU5YWI3NGQ0YWNkNmYuc2V0Q29udGVudChodG1sXzU0YTI0NDg0NTExNDQxYzM5MTdhNmUwYTQ4NzNjOGY2KTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyX2ViMzU3ZTlhNDFkMzRhMWVhNDhmOGJlMTQyZWNkOTg5LmJpbmRQb3B1cChwb3B1cF9lMGJjOGI2MzBjYjc0ODY2ODhiNTlhYjc0ZDRhY2Q2Zik7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9mMTllNDBiZmY5Y2E0M2VhYjlkOGRlYmI0NTcyNTJiZCA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY3OTU2MjYsLTc5LjM3NzUyOTQwMDAwMDAxXSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiNmZjAwMDAiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjZmYwMDAwIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzMyYjJkOTQ4MDI5NjRiM2U4NGY3Y2QwNzc5Y2RlZDA0ID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzY0ODg0ZTVkNDlmMDRmMjg5ZjAxMjQwMDM2MDkyMjY0ID0gJCgnPGRpdiBpZD0iaHRtbF82NDg4NGU1ZDQ5ZjA0ZjI4OWYwMTI0MDAzNjA5MjI2NCIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgMDwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfMzJiMmQ5NDgwMjk2NGIzZTg0ZjdjZDA3NzljZGVkMDQuc2V0Q29udGVudChodG1sXzY0ODg0ZTVkNDlmMDRmMjg5ZjAxMjQwMDM2MDkyMjY0KTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyX2YxOWU0MGJmZjljYTQzZWFiOWQ4ZGViYjQ1NzI1MmJkLmJpbmRQb3B1cChwb3B1cF8zMmIyZDk0ODAyOTY0YjNlODRmN2NkMDc3OWNkZWQwNCk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9kNTMzZGJhMmU3MzI0MTEwYjJhZmMwNmIzY2MxN2IzMCA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY0NjQzNTIsLTc5LjM3NDg0NTk5OTk5OTk5XSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiNmZjAwMDAiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjZmYwMDAwIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwX2JjYTRmNTRkNjMwYjQxMDM4MTk0N2RhMDc5MTBlOTliID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzNhYzRhNzYzMmQzNjQ0NjNiMTVhN2UwZDU2YmE4NmMwID0gJCgnPGRpdiBpZD0iaHRtbF8zYWM0YTc2MzJkMzY0NDYzYjE1YTdlMGQ1NmJhODZjMCIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgMDwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfYmNhNGY1NGQ2MzBiNDEwMzgxOTQ3ZGEwNzkxMGU5OWIuc2V0Q29udGVudChodG1sXzNhYzRhNzYzMmQzNjQ0NjNiMTVhN2UwZDU2YmE4NmMwKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyX2Q1MzNkYmEyZTczMjQxMTBiMmFmYzA2YjNjYzE3YjMwLmJpbmRQb3B1cChwb3B1cF9iY2E0ZjU0ZDYzMGI0MTAzODE5NDdkYTA3OTEwZTk5Yik7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9hOWNlZTI4MzBjYjg0ZWU0Yjg3YTJkOWY0ZWE4Njc3MSA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY2Nzk2NywtNzkuMzY3Njc1M10sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICIjZmYwMDAwIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiI2ZmMDAwMCIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYyk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF9mOWMwM2JiM2VjNjU0ZWI2OWI5YTVmZTIwMTQ4YTBmNiA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9lZWJkMjExYjU5MzE0ZjY2ODEyYTgyZTQ1NjBiY2Q5NiA9ICQoJzxkaXYgaWQ9Imh0bWxfZWViZDIxMWI1OTMxNGY2NjgxMmE4MmU0NTYwYmNkOTYiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPiBDbHVzdGVyIDA8L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwX2Y5YzAzYmIzZWM2NTRlYjY5YjlhNWZlMjAxNDhhMGY2LnNldENvbnRlbnQoaHRtbF9lZWJkMjExYjU5MzE0ZjY2ODEyYTgyZTQ1NjBiY2Q5Nik7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl9hOWNlZTI4MzBjYjg0ZWU0Yjg3YTJkOWY0ZWE4Njc3MS5iaW5kUG9wdXAocG9wdXBfZjljMDNiYjNlYzY1NGViNjliOWE1ZmUyMDE0OGEwZjYpOwoKICAgICAgICAgICAgCiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGNpcmNsZV9tYXJrZXJfNDhlMDg5ZjA4MDhhNDljN2FhNDY5NDI4ZDE4ZTlkYTUgPSBMLmNpcmNsZU1hcmtlcigKICAgICAgICAgICAgICAgIFs0My42NDg0MjkyLC03OS4zODIyODAyXSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiNmZjAwMDAiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjZmYwMDAwIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwXzY1ZjAzNGZmMDc2OTRhM2ZiOWU3MmRkMGNmNTZkNTAwID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzJhZjE0OGU0NmRiMjRlODI4N2FjMzY1ZjIzMzJiOTZlID0gJCgnPGRpdiBpZD0iaHRtbF8yYWYxNDhlNDZkYjI0ZTgyODdhYzM2NWYyMzMyYjk2ZSIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgMDwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfNjVmMDM0ZmYwNzY5NGEzZmI5ZTcyZGQwY2Y1NmQ1MDAuc2V0Q29udGVudChodG1sXzJhZjE0OGU0NmRiMjRlODI4N2FjMzY1ZjIzMzJiOTZlKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyXzQ4ZTA4OWYwODA4YTQ5YzdhYTQ2OTQyOGQxOGU5ZGE1LmJpbmRQb3B1cChwb3B1cF82NWYwMzRmZjA3Njk0YTNmYjllNzJkZDBjZjU2ZDUwMCk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9lYTk3ODAzM2NiN2Y0MTgxOTE1MzgyMmNlNTY4NWFlMSA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY2NTg1OTksLTc5LjM4MzE1OTkwMDAwMDAxXSwKICAgICAgICAgICAgICAgIHsKICAiYnViYmxpbmdNb3VzZUV2ZW50cyI6IHRydWUsCiAgImNvbG9yIjogIiNmZjAwMDAiLAogICJkYXNoQXJyYXkiOiBudWxsLAogICJkYXNoT2Zmc2V0IjogbnVsbCwKICAiZmlsbCI6IHRydWUsCiAgImZpbGxDb2xvciI6ICIjZmYwMDAwIiwKICAiZmlsbE9wYWNpdHkiOiAwLjcsCiAgImZpbGxSdWxlIjogImV2ZW5vZGQiLAogICJsaW5lQ2FwIjogInJvdW5kIiwKICAibGluZUpvaW4iOiAicm91bmQiLAogICJvcGFjaXR5IjogMS4wLAogICJyYWRpdXMiOiA1LAogICJzdHJva2UiOiB0cnVlLAogICJ3ZWlnaHQiOiAzCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwXzYxNjE1NzlkNzI2NjQ0MDg5ZGZmNmY0YjA3MzgyNTBjKTsKICAgICAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIHBvcHVwX2ZhYjBkYTg2Yzg1YTQ1ZTI5ZjQwNDk5ZTZmMjU4OWU1ID0gTC5wb3B1cCh7bWF4V2lkdGg6ICczMDAnfSk7CgogICAgICAgICAgICAKICAgICAgICAgICAgICAgIHZhciBodG1sXzFlYzQ0N2Y5ZTY4NDQ0Y2M4ZjE3YzVmMGY5ZjBlYjIxID0gJCgnPGRpdiBpZD0iaHRtbF8xZWM0NDdmOWU2ODQ0NGNjOGYxN2M1ZjBmOWYwZWIyMSIgc3R5bGU9IndpZHRoOiAxMDAuMCU7IGhlaWdodDogMTAwLjAlOyI+IENsdXN0ZXIgMDwvZGl2PicpWzBdOwogICAgICAgICAgICAgICAgcG9wdXBfZmFiMGRhODZjODVhNDVlMjlmNDA0OTllNmYyNTg5ZTUuc2V0Q29udGVudChodG1sXzFlYzQ0N2Y5ZTY4NDQ0Y2M4ZjE3YzVmMGY5ZjBlYjIxKTsKICAgICAgICAgICAgCgogICAgICAgICAgICBjaXJjbGVfbWFya2VyX2VhOTc4MDMzY2I3ZjQxODE5MTUzODIyY2U1Njg1YWUxLmJpbmRQb3B1cChwb3B1cF9mYWIwZGE4NmM4NWE0NWUyOWY0MDQ5OWU2ZjI1ODllNSk7CgogICAgICAgICAgICAKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgY2lyY2xlX21hcmtlcl9jNWE3ZjQwYzM3OTY0ZTdiOTdlOGE4YzdiNWNkNGJkNSA9IEwuY2lyY2xlTWFya2VyKAogICAgICAgICAgICAgICAgWzQzLjY2Mjc0MzksLTc5LjMyMTU1OF0sCiAgICAgICAgICAgICAgICB7CiAgImJ1YmJsaW5nTW91c2VFdmVudHMiOiB0cnVlLAogICJjb2xvciI6ICIjZmZiMzYwIiwKICAiZGFzaEFycmF5IjogbnVsbCwKICAiZGFzaE9mZnNldCI6IG51bGwsCiAgImZpbGwiOiB0cnVlLAogICJmaWxsQ29sb3IiOiAiI2ZmYjM2MCIsCiAgImZpbGxPcGFjaXR5IjogMC43LAogICJmaWxsUnVsZSI6ICJldmVub2RkIiwKICAibGluZUNhcCI6ICJyb3VuZCIsCiAgImxpbmVKb2luIjogInJvdW5kIiwKICAib3BhY2l0eSI6IDEuMCwKICAicmFkaXVzIjogNSwKICAic3Ryb2tlIjogdHJ1ZSwKICAid2VpZ2h0IjogMwp9CiAgICAgICAgICAgICAgICApLmFkZFRvKG1hcF82MTYxNTc5ZDcyNjY0NDA4OWRmZjZmNGIwNzM4MjUwYyk7CiAgICAgICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBwb3B1cF8wNTQyMjQ1NDFmZWM0MzcwOTA2YTYwODJjNWE0NzMzZCA9IEwucG9wdXAoe21heFdpZHRoOiAnMzAwJ30pOwoKICAgICAgICAgICAgCiAgICAgICAgICAgICAgICB2YXIgaHRtbF9lNDcyYmI1NzcwM2I0ZDMzYjk3ZDJhYTA3ZjQ4ZGFhOSA9ICQoJzxkaXYgaWQ9Imh0bWxfZTQ3MmJiNTc3MDNiNGQzM2I5N2QyYWEwN2Y0OGRhYTkiIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPiBDbHVzdGVyIDQ8L2Rpdj4nKVswXTsKICAgICAgICAgICAgICAgIHBvcHVwXzA1NDIyNDU0MWZlYzQzNzA5MDZhNjA4MmM1YTQ3MzNkLnNldENvbnRlbnQoaHRtbF9lNDcyYmI1NzcwM2I0ZDMzYjk3ZDJhYTA3ZjQ4ZGFhOSk7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgY2lyY2xlX21hcmtlcl9jNWE3ZjQwYzM3OTY0ZTdiOTdlOGE4YzdiNWNkNGJkNS5iaW5kUG9wdXAocG9wdXBfMDU0MjI0NTQxZmVjNDM3MDkwNmE2MDgyYzVhNDczM2QpOwoKICAgICAgICAgICAgCiAgICAgICAgCjwvc2NyaXB0Pg== onload="this.contentDocument.open();this.contentDocument.write(atob(this.getAttribute('data-html')));this.contentDocument.close();" allowfullscreen webkitallowfullscreen mozallowfullscreen></iframe></div></div>




```python

```


```python

```


```python

```
