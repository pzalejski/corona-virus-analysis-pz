<img id='Intro' src="https://global.unitednations.entermediadb.net/assets/mediadb/services/module/asset/downloads/preset/Libraries/Production+Library/31-01-20-coronavirus-digital-image-cdc1.jpg/image1440x560cropped.jpg">
<i>Image Credits: <a href="https://news.un.org/en/story/2020/02/1056562">United Nations</a>
   

> Coronavirus disease (COVID-19) is an infectious disease caused by a newly discovered coronavirus.<br><br>
Most people infected with the COVID-19 virus will experience mild to moderate respiratory illness and recover without requiring special treatment.  Older people, and those with underlying medical problems like cardiovascular disease, diabetes, chronic respiratory disease, and cancer are more likely to develop serious illness.<br><br>
The best way to prevent and slow down transmission is be well informed about the COVID-19 virus, the disease it causes and how it spreads. Protect yourself and others from infection by washing your hands or using an alcohol based rub frequently and not touching your face. <br><br>The COVID-19 virus spreads primarily through droplets of saliva or discharge from the nose when an infected person coughs or sneezes, so it’s important that you also practice respiratory etiquette (for example, by coughing into a flexed elbow).


<style>
div.output_area .rendered_html table {
    margin-left: auto;
    margin-right: auto;
}
</style>




<script type="text/javascript">
window.PlotlyConfig = {MathJaxConfig: 'local'};
if (window.MathJax) {MathJax.Hub.Config({SVG: {font: "STIX-Web"}});}
if (typeof require !== 'undefined') {
require.undef("plotly");
requirejs.config({
    paths: {
        'plotly': ['https://cdn.plot.ly/plotly-latest.min']
    }
});
require(['plotly'], function(Plotly) {
    window._Plotly = Plotly;
});
}
</script>



## Data
***
<a id='Data' href="https://github.com/CSSEGISandData/COVID-19">https://github.com/CSSEGISandData/COVID-19</a>
<br>
This is the data repository for the 2019 Novel Coronavirus Visual Dashboard operated by the Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE). Dataset is updated on a daily basis by John Hopkins CSSE.
<div id='Content'></div>

# Content:
***
<ul>
    <li><a href="#Intro">Intro</a></li>
    <li><a href='#LatestContinent'>Latest Reported Cases by Continent</a></li>
    <li><a href='#Combined'>Combined Reported Cases, Deaths, Recoveries</a></li>
    <li><a href='#LatestCountry'>Latest Reported Cases by Country</a></li>
    <li><a href='#m_and_d_rates'>Mortality and Recovery Rates</a></li>
    <li><a href='#daily_increase'>Daily Increases</a></li>
</ul>

## Imports:
***
<ul id='Imports'>
    <li>Pandas</li>
    <li>Numpy</li>
    <li>Plotly</li>
    <li>Matplotlib</li>
</ul>


## Sample Dataset snipits:
***




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
      <th>Province/State</th>
      <th>Lat</th>
      <th>Long</th>
      <th>1/22/20</th>
      <th>1/23/20</th>
      <th>1/24/20</th>
      <th>1/25/20</th>
      <th>1/26/20</th>
      <th>1/27/20</th>
      <th>1/28/20</th>
      <th>...</th>
      <th>4/20/20</th>
      <th>4/21/20</th>
      <th>4/22/20</th>
      <th>4/23/20</th>
      <th>4/24/20</th>
      <th>4/25/20</th>
      <th>4/26/20</th>
      <th>4/27/20</th>
      <th>4/28/20</th>
      <th>4/29/20</th>
    </tr>
    <tr>
      <th>Country/Region</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>US</th>
      <td>NaN</td>
      <td>37.0902</td>
      <td>-95.7129</td>
      <td>1</td>
      <td>1</td>
      <td>2</td>
      <td>2</td>
      <td>5</td>
      <td>5</td>
      <td>5</td>
      <td>...</td>
      <td>784326</td>
      <td>811865</td>
      <td>840351</td>
      <td>869170</td>
      <td>905358</td>
      <td>938154</td>
      <td>965785</td>
      <td>988197</td>
      <td>1012582</td>
      <td>1039909</td>
    </tr>
    <tr>
      <th>Spain</th>
      <td>NaN</td>
      <td>40.0000</td>
      <td>-4.0000</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>200210</td>
      <td>204178</td>
      <td>208389</td>
      <td>213024</td>
      <td>202990</td>
      <td>205905</td>
      <td>207634</td>
      <td>209465</td>
      <td>210773</td>
      <td>212917</td>
    </tr>
    <tr>
      <th>Italy</th>
      <td>NaN</td>
      <td>43.0000</td>
      <td>12.0000</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>181228</td>
      <td>183957</td>
      <td>187327</td>
      <td>189973</td>
      <td>192994</td>
      <td>195351</td>
      <td>197675</td>
      <td>199414</td>
      <td>201505</td>
      <td>203591</td>
    </tr>
    <tr>
      <th>France</th>
      <td>NaN</td>
      <td>46.2276</td>
      <td>2.2137</td>
      <td>0</td>
      <td>0</td>
      <td>2</td>
      <td>3</td>
      <td>3</td>
      <td>3</td>
      <td>4</td>
      <td>...</td>
      <td>154188</td>
      <td>156921</td>
      <td>154715</td>
      <td>157026</td>
      <td>158636</td>
      <td>160292</td>
      <td>160847</td>
      <td>164589</td>
      <td>167605</td>
      <td>165093</td>
    </tr>
    <tr>
      <th>Germany</th>
      <td>NaN</td>
      <td>51.0000</td>
      <td>9.0000</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>4</td>
      <td>...</td>
      <td>147065</td>
      <td>148291</td>
      <td>150648</td>
      <td>153129</td>
      <td>154999</td>
      <td>156513</td>
      <td>157770</td>
      <td>158758</td>
      <td>159912</td>
      <td>161539</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 102 columns</p>
</div>



    Confirmed
    




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
      <th>Province/State</th>
      <th>Lat</th>
      <th>Long</th>
      <th>1/22/20</th>
      <th>1/23/20</th>
      <th>1/24/20</th>
      <th>1/25/20</th>
      <th>1/26/20</th>
      <th>1/27/20</th>
      <th>1/28/20</th>
      <th>...</th>
      <th>4/20/20</th>
      <th>4/21/20</th>
      <th>4/22/20</th>
      <th>4/23/20</th>
      <th>4/24/20</th>
      <th>4/25/20</th>
      <th>4/26/20</th>
      <th>4/27/20</th>
      <th>4/28/20</th>
      <th>4/29/20</th>
    </tr>
    <tr>
      <th>Country/Region</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>US</th>
      <td>NaN</td>
      <td>37.0902</td>
      <td>-95.7129</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>42659</td>
      <td>45086</td>
      <td>47412</td>
      <td>49724</td>
      <td>51493</td>
      <td>53755</td>
      <td>54881</td>
      <td>56259</td>
      <td>58355</td>
      <td>60967</td>
    </tr>
    <tr>
      <th>Italy</th>
      <td>NaN</td>
      <td>43.0000</td>
      <td>12.0000</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>24114</td>
      <td>24648</td>
      <td>25085</td>
      <td>25549</td>
      <td>25969</td>
      <td>26384</td>
      <td>26644</td>
      <td>26977</td>
      <td>27359</td>
      <td>27682</td>
    </tr>
    <tr>
      <th>United Kingdom</th>
      <td>NaN</td>
      <td>55.3781</td>
      <td>-3.4360</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>19051</td>
      <td>20223</td>
      <td>21060</td>
      <td>21787</td>
      <td>22792</td>
      <td>23635</td>
      <td>24055</td>
      <td>24393</td>
      <td>25302</td>
      <td>26097</td>
    </tr>
    <tr>
      <th>Spain</th>
      <td>NaN</td>
      <td>40.0000</td>
      <td>-4.0000</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>20852</td>
      <td>21282</td>
      <td>21717</td>
      <td>22157</td>
      <td>22524</td>
      <td>22902</td>
      <td>23190</td>
      <td>23521</td>
      <td>23822</td>
      <td>24275</td>
    </tr>
    <tr>
      <th>France</th>
      <td>NaN</td>
      <td>46.2276</td>
      <td>2.2137</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>20265</td>
      <td>20796</td>
      <td>21340</td>
      <td>21856</td>
      <td>22245</td>
      <td>22614</td>
      <td>22856</td>
      <td>23293</td>
      <td>23660</td>
      <td>24087</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 102 columns</p>
</div>



    Deaths
    




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
      <th>Province/State</th>
      <th>Lat</th>
      <th>Long</th>
      <th>1/22/20</th>
      <th>1/23/20</th>
      <th>1/24/20</th>
      <th>1/25/20</th>
      <th>1/26/20</th>
      <th>1/27/20</th>
      <th>1/28/20</th>
      <th>...</th>
      <th>4/20/20</th>
      <th>4/21/20</th>
      <th>4/22/20</th>
      <th>4/23/20</th>
      <th>4/24/20</th>
      <th>4/25/20</th>
      <th>4/26/20</th>
      <th>4/27/20</th>
      <th>4/28/20</th>
      <th>4/29/20</th>
    </tr>
    <tr>
      <th>Country/Region</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Germany</th>
      <td>NaN</td>
      <td>51.0000</td>
      <td>9.0000</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>91500</td>
      <td>95200</td>
      <td>99400</td>
      <td>103300</td>
      <td>109800</td>
      <td>109800</td>
      <td>112000</td>
      <td>114500</td>
      <td>117400</td>
      <td>120400</td>
    </tr>
    <tr>
      <th>US</th>
      <td>NaN</td>
      <td>37.0902</td>
      <td>-95.7129</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>72329</td>
      <td>75204</td>
      <td>77366</td>
      <td>80203</td>
      <td>99079</td>
      <td>100372</td>
      <td>106988</td>
      <td>111424</td>
      <td>115936</td>
      <td>120720</td>
    </tr>
    <tr>
      <th>Spain</th>
      <td>NaN</td>
      <td>40.0000</td>
      <td>-4.0000</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>80587</td>
      <td>82514</td>
      <td>85915</td>
      <td>89250</td>
      <td>92355</td>
      <td>95708</td>
      <td>98372</td>
      <td>100875</td>
      <td>102548</td>
      <td>108947</td>
    </tr>
    <tr>
      <th>Iran</th>
      <td>NaN</td>
      <td>32.0000</td>
      <td>53.0000</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>59273</td>
      <td>60965</td>
      <td>63113</td>
      <td>64843</td>
      <td>66599</td>
      <td>68193</td>
      <td>69657</td>
      <td>70933</td>
      <td>72439</td>
      <td>73791</td>
    </tr>
    <tr>
      <th>Italy</th>
      <td>NaN</td>
      <td>43.0000</td>
      <td>12.0000</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
      <td>...</td>
      <td>48877</td>
      <td>51600</td>
      <td>54543</td>
      <td>57576</td>
      <td>60498</td>
      <td>63120</td>
      <td>64928</td>
      <td>66624</td>
      <td>68941</td>
      <td>71252</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 102 columns</p>
</div>



    Recovered
    




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
      <th>FIPS</th>
      <th>Admin2</th>
      <th>Province_State</th>
      <th>Country/Region</th>
      <th>Last_Update</th>
      <th>Lat</th>
      <th>Long_</th>
      <th>Confirmed</th>
      <th>Deaths</th>
      <th>Recovered</th>
      <th>Active</th>
      <th>Combined_Key</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>45001.0</td>
      <td>Abbeville</td>
      <td>South Carolina</td>
      <td>US</td>
      <td>2020-04-30 02:32:27</td>
      <td>34.223334</td>
      <td>-82.461707</td>
      <td>29</td>
      <td>0</td>
      <td>0</td>
      <td>29</td>
      <td>Abbeville, South Carolina, US</td>
    </tr>
    <tr>
      <th>1</th>
      <td>22001.0</td>
      <td>Acadia</td>
      <td>Louisiana</td>
      <td>US</td>
      <td>2020-04-30 02:32:27</td>
      <td>30.295065</td>
      <td>-92.414197</td>
      <td>130</td>
      <td>9</td>
      <td>0</td>
      <td>121</td>
      <td>Acadia, Louisiana, US</td>
    </tr>
    <tr>
      <th>2</th>
      <td>51001.0</td>
      <td>Accomack</td>
      <td>Virginia</td>
      <td>US</td>
      <td>2020-04-30 02:32:27</td>
      <td>37.767072</td>
      <td>-75.632346</td>
      <td>229</td>
      <td>4</td>
      <td>0</td>
      <td>225</td>
      <td>Accomack, Virginia, US</td>
    </tr>
    <tr>
      <th>3</th>
      <td>16001.0</td>
      <td>Ada</td>
      <td>Idaho</td>
      <td>US</td>
      <td>2020-04-30 02:32:27</td>
      <td>43.452658</td>
      <td>-116.241552</td>
      <td>662</td>
      <td>16</td>
      <td>0</td>
      <td>646</td>
      <td>Ada, Idaho, US</td>
    </tr>
    <tr>
      <th>4</th>
      <td>19001.0</td>
      <td>Adair</td>
      <td>Iowa</td>
      <td>US</td>
      <td>2020-04-30 02:32:27</td>
      <td>41.330756</td>
      <td>-94.471059</td>
      <td>1</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
      <td>Adair, Iowa, US</td>
    </tr>
  </tbody>
</table>
</div>



    Latest Data
    

<div id='LatestContinent'></div>

<div><h2 style='display:inline'>Latest Reported Cases by Continent:</h2><a href='#Content' style='float:right; display:inline'>Return to Content</a></div>

***




<style  type="text/css" >
    #T_234fba55_8b42_11ea_8521_50e0853f99e9row0_col0 {
            background-color:  #fdfdfd;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row0_col1 {
            background-color:  #fff4ee;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row0_col2 {
            background-color:  #f5fbf2;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row0_col3 {
            background-color:  #f3f8fe;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row0_col4 {
            background-color:  #fda965;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row1_col0 {
            background-color:  #d8d8d8;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row1_col1 {
            background-color:  #fee3d6;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row1_col2 {
            background-color:  #9cd797;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row1_col3 {
            background-color:  #d5e5f4;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row1_col4 {
            background-color:  #fdba7f;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row2_col0 {
            background-color:  #000000;
            color:  #f1f1f1;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row2_col1 {
            background-color:  #67000d;
            color:  #f1f1f1;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row2_col2 {
            background-color:  #00441b;
            color:  #f1f1f1;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row2_col3 {
            background-color:  #084e98;
            color:  #f1f1f1;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row2_col4 {
            background-color:  #7f2704;
            color:  #f1f1f1;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row3_col0 {
            background-color:  #4b4b4b;
            color:  #f1f1f1;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row3_col1 {
            background-color:  #fb6d4d;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row3_col2 {
            background-color:  #bbe4b4;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row3_col3 {
            background-color:  #08306b;
            color:  #f1f1f1;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row3_col4 {
            background-color:  #f67723;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row4_col0 {
            background-color:  #ffffff;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row4_col1 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row4_col2 {
            background-color:  #f6fcf4;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row4_col3 {
            background-color:  #f7fbff;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row4_col4 {
            background-color:  #fff5eb;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row5_col0 {
            background-color:  #ffffff;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row5_col1 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row5_col2 {
            background-color:  #f7fcf5;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row5_col3 {
            background-color:  #f6faff;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row5_col4 {
            background-color:  #fdc088;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row6_col0 {
            background-color:  #f2f2f2;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row6_col1 {
            background-color:  #ffebe2;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row6_col2 {
            background-color:  #e8f6e4;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row6_col3 {
            background-color:  #e1edf8;
            color:  #000000;
        }    #T_234fba55_8b42_11ea_8521_50e0853f99e9row6_col4 {
            background-color:  #fd9a4e;
            color:  #000000;
        }</style><table id="T_234fba55_8b42_11ea_8521_50e0853f99e9" ><thead>    <tr>        <th class="blank level0" ></th>        <th class="col_heading level0 col0" >Confirmed</th>        <th class="col_heading level0 col1" >Deaths</th>        <th class="col_heading level0 col2" >Recovered</th>        <th class="col_heading level0 col3" >Active</th>        <th class="col_heading level0 col4" >Mortality Rate</th>    </tr>    <tr>        <th class="index_name level0" >Continent</th>        <th class="blank" ></th>        <th class="blank" ></th>        <th class="blank" ></th>        <th class="blank" ></th>        <th class="blank" ></th>    </tr></thead><tbody>
                <tr>
                        <th id="T_234fba55_8b42_11ea_8521_50e0853f99e9level0_row0" class="row_heading level0 row0" >Africa</th>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row0_col0" class="data row0 col0" >34802</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row0_col1" class="data row0 col1" >1541</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row0_col2" class="data row0 col2" >11407</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row0_col3" class="data row0 col3" >21854</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row0_col4" class="data row0 col4" >4.430000</td>
            </tr>
            <tr>
                        <th id="T_234fba55_8b42_11ea_8521_50e0853f99e9level0_row1" class="row_heading level0 row1" >Asia</th>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row1_col0" class="data row1 col0" >381032</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row1_col1" class="data row1 col1" >15090</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row1_col2" class="data row1 col2" >208650</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row1_col3" class="data row1 col3" >157292</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row1_col4" class="data row1 col4" >3.960000</td>
            </tr>
            <tr>
                        <th id="T_234fba55_8b42_11ea_8521_50e0853f99e9level0_row2" class="row_heading level0 row2" >Europe</th>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row2_col0" class="data row2 col0" >1468112</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row2_col1" class="data row2 col1" >135939</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row2_col2" class="data row2 col2" >530210</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row2_col3" class="data row2 col3" >801963</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row2_col4" class="data row2 col4" >9.260000</td>
            </tr>
            <tr>
                        <th id="T_234fba55_8b42_11ea_8521_50e0853f99e9level0_row3" class="row_heading level0 row3" >North America</th>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row3_col0" class="data row3 col0" >1127906</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row3_col1" class="data row3 col1" >66517</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row3_col2" class="data row3 col2" >155603</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row3_col3" class="data row3 col3" >905786</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row3_col4" class="data row3 col4" >5.900000</td>
            </tr>
            <tr>
                        <th id="T_234fba55_8b42_11ea_8521_50e0853f99e9level0_row4" class="row_heading level0 row4" >Oceania</th>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row4_col0" class="data row4 col0" >8254</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row4_col1" class="data row4 col1" >110</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row4_col2" class="data row4 col2" >6968</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row4_col3" class="data row4 col3" >1176</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row4_col4" class="data row4 col4" >1.330000</td>
            </tr>
            <tr>
                        <th id="T_234fba55_8b42_11ea_8521_50e0853f99e9level0_row5" class="row_heading level0 row5" >Others</th>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row5_col0" class="data row5 col0" >7714</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row5_col1" class="data row5 col1" >292</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row5_col2" class="data row5 col2" >2696</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row5_col3" class="data row5 col3" >4726</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row5_col4" class="data row5 col4" >3.790000</td>
            </tr>
            <tr>
                        <th id="T_234fba55_8b42_11ea_8521_50e0853f99e9level0_row6" class="row_heading level0 row6" >South America</th>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row6_col0" class="data row6 col0" >166066</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row6_col1" class="data row6 col1" >8149</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row6_col2" class="data row6 col2" >57185</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row6_col3" class="data row6 col3" >100732</td>
                        <td id="T_234fba55_8b42_11ea_8521_50e0853f99e9row6_col4" class="data row6 col4" >4.910000</td>
            </tr>
    </tbody></table>




<div>


            <div id="46ac30c5-98b1-4df2-bd11-9888302c4bdc" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("46ac30c5-98b1-4df2-bd11-9888302c4bdc")) {
                    Plotly.newPlot(
                        '46ac30c5-98b1-4df2-bd11-9888302c4bdc',
                        [{"marker": {"color": "orange"}, "orientation": "h", "type": "bar", "x": [7714, 8254, 34802, 166066, 381032, 1127906, 1468112], "y": ["Others", "Oceania", "Africa", "South America", "Asia", "North America", "Europe"]}],
                        {"template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "Confirmed Cases by Continent"}, "xaxis": {"title": {"text": "Number of cases"}}, "yaxis": {"title": {"text": "Continents"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('46ac30c5-98b1-4df2-bd11-9888302c4bdc');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="40608720-cf5e-4955-9f2f-9a808d10aa32" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("40608720-cf5e-4955-9f2f-9a808d10aa32")) {
                    Plotly.newPlot(
                        '40608720-cf5e-4955-9f2f-9a808d10aa32',
                        [{"marker": {"color": "red"}, "orientation": "h", "type": "bar", "x": [110, 292, 1541, 8149, 15090, 66517, 135939], "y": ["Oceania", "Others", "Africa", "South America", "Asia", "North America", "Europe"]}],
                        {"template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "Deaths by Continent"}, "xaxis": {"title": {"text": "Number of cases"}}, "yaxis": {"title": {"text": "Continents"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('40608720-cf5e-4955-9f2f-9a808d10aa32');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="61c76582-e742-465e-b1e8-78b597663766" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("61c76582-e742-465e-b1e8-78b597663766")) {
                    Plotly.newPlot(
                        '61c76582-e742-465e-b1e8-78b597663766',
                        [{"marker": {"color": "green"}, "orientation": "h", "type": "bar", "x": [110, 292, 1541, 8149, 15090, 66517, 135939], "y": ["Oceania", "Others", "Africa", "South America", "Asia", "North America", "Europe"]}],
                        {"template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "Recoveries by Continent"}, "xaxis": {"title": {"text": "Number of cases"}}, "yaxis": {"title": {"text": "Continents"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('61c76582-e742-465e-b1e8-78b597663766');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>


<div id='LatestCountry'></div>

<div><h2 style='display:inline'>Latest Reported Cases by Country:</h2><a href='#Content' style='float:right; display:inline'>Return to Content</a></div>

***




<style  type="text/css" >
    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row0_col0 {
            background-color:  #000000;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row0_col1 {
            background-color:  #67000d;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row0_col2 {
            background-color:  #006227;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row0_col3 {
            background-color:  #08306b;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row0_col4 {
            background-color:  #fdb06e;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row0_col5 {
            background-color:  #e5f5e1;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row1_col0 {
            background-color:  #dfdfdf;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row1_col1 {
            background-color:  #fc8b6b;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row1_col2 {
            background-color:  #00441b;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row1_col3 {
            background-color:  #e5eff9;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row1_col4 {
            background-color:  #ec620f;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row1_col5 {
            background-color:  #4bb062;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row2_col0 {
            background-color:  #e5e5e5;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row2_col1 {
            background-color:  #fb7858;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row2_col2 {
            background-color:  #65bd6f;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row2_col3 {
            background-color:  #dfecf7;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row2_col4 {
            background-color:  #a93703;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row2_col5 {
            background-color:  #a2d99c;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row3_col0 {
            background-color:  #ececec;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row3_col1 {
            background-color:  #fc8b6b;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row3_col2 {
            background-color:  #a3da9d;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row3_col3 {
            background-color:  #e2edf8;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row3_col4 {
            background-color:  #973003;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row3_col5 {
            background-color:  #b4e1ad;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row4_col0 {
            background-color:  #ececec;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row4_col1 {
            background-color:  #fc8161;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row4_col2 {
            background-color:  #f6fcf4;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row4_col3 {
            background-color:  #d7e6f5;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row4_col4 {
            background-color:  #7f2704;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row4_col5 {
            background-color:  #f7fcf5;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row5_col0 {
            background-color:  #ededed;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row5_col1 {
            background-color:  #fee3d7;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row5_col2 {
            background-color:  #006328;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row5_col3 {
            background-color:  #eff6fc;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row5_col4 {
            background-color:  #fdd0a2;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row5_col5 {
            background-color:  #16803c;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row6_col0 {
            background-color:  #f3f3f3;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row6_col1 {
            background-color:  #ffede5;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row6_col2 {
            background-color:  #afdfa8;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row6_col3 {
            background-color:  #e7f1fa;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row6_col4 {
            background-color:  #fee0c1;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row6_col5 {
            background-color:  #98d594;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row7_col0 {
            background-color:  #f5f5f5;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row7_col1 {
            background-color:  #fff2ec;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row7_col2 {
            background-color:  #ecf8e8;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row7_col3 {
            background-color:  #e3eef8;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row7_col4 {
            background-color:  #ffeede;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row7_col5 {
            background-color:  #e8f6e3;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row8_col0 {
            background-color:  #f6f6f6;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row8_col1 {
            background-color:  #fee5d9;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row8_col2 {
            background-color:  #5db96b;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row8_col3 {
            background-color:  #f5f9fe;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row8_col4 {
            background-color:  #fda762;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row8_col5 {
            background-color:  #097532;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row9_col0 {
            background-color:  #f7f7f7;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row9_col1 {
            background-color:  #fee8de;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row9_col2 {
            background-color:  #4eb264;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row9_col3 {
            background-color:  #f7fbff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row9_col4 {
            background-color:  #fdb678;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row9_col5 {
            background-color:  #00441b;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row10_col0 {
            background-color:  #f7f7f7;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row10_col1 {
            background-color:  #fee6da;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row10_col2 {
            background-color:  #c6e8bf;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row10_col3 {
            background-color:  #eef5fc;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row10_col4 {
            background-color:  #fd9e54;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row10_col5 {
            background-color:  #84cc83;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row11_col0 {
            background-color:  #fbfbfb;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row11_col1 {
            background-color:  #ffece4;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row11_col2 {
            background-color:  #dff3da;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row11_col3 {
            background-color:  #f1f7fd;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row11_col4 {
            background-color:  #fdae6a;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row11_col5 {
            background-color:  #95d391;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row12_col0 {
            background-color:  #fbfbfb;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row12_col1 {
            background-color:  #fee1d3;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row12_col2 {
            background-color:  #ebf7e7;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row12_col3 {
            background-color:  #f1f7fd;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row12_col4 {
            background-color:  #7f2704;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row12_col5 {
            background-color:  #c8e9c1;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row13_col0 {
            background-color:  #fcfcfc;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row13_col1 {
            background-color:  #fee8de;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row13_col2 {
            background-color:  #f7fcf5;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row13_col3 {
            background-color:  #f0f6fd;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row13_col4 {
            background-color:  #d04501;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row13_col5 {
            background-color:  #f7fcf5;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row14_col0 {
            background-color:  #fdfdfd;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row14_col1 {
            background-color:  #fff3ed;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row14_col2 {
            background-color:  #ecf8e8;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row14_col3 {
            background-color:  #f2f8fd;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row14_col4 {
            background-color:  #fedebd;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row14_col5 {
            background-color:  #b4e1ad;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row15_col0 {
            background-color:  #fdfdfd;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row15_col1 {
            background-color:  #fff2ec;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row15_col2 {
            background-color:  #eef8ea;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row15_col3 {
            background-color:  #f2f8fd;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row15_col4 {
            background-color:  #fdd9b4;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row15_col5 {
            background-color:  #c1e6ba;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row16_col0 {
            background-color:  #fdfdfd;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row16_col1 {
            background-color:  #fff0e9;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row16_col2 {
            background-color:  #dbf1d5;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row16_col3 {
            background-color:  #f6faff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row16_col4 {
            background-color:  #fdb06e;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row16_col5 {
            background-color:  #0e7936;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row17_col0 {
            background-color:  #fefefe;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row17_col1 {
            background-color:  #fff3ed;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row17_col2 {
            background-color:  #f6fcf4;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row17_col3 {
            background-color:  #f2f8fd;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row17_col4 {
            background-color:  #fdd5ab;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row17_col5 {
            background-color:  #eef8ea;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row18_col0 {
            background-color:  #fefefe;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row18_col1 {
            background-color:  #fff2ec;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row18_col2 {
            background-color:  #f6fcf4;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row18_col3 {
            background-color:  #f2f8fd;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row18_col4 {
            background-color:  #fdd1a3;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row18_col5 {
            background-color:  #eff9eb;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row19_col0 {
            background-color:  #fefefe;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row19_col1 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row19_col2 {
            background-color:  #f4fbf2;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row19_col3 {
            background-color:  #f3f8fe;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row19_col4 {
            background-color:  #fff0e2;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row19_col5 {
            background-color:  #e0f3db;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row20_col0 {
            background-color:  #ffffff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row20_col1 {
            background-color:  #ffeee7;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row20_col2 {
            background-color:  #f6fcf4;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row20_col3 {
            background-color:  #f4f9fe;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row20_col4 {
            background-color:  #d04501;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row20_col5 {
            background-color:  #f0f9ed;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row21_col0 {
            background-color:  #ffffff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row21_col1 {
            background-color:  #fff2ec;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row21_col2 {
            background-color:  #e9f7e5;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row21_col3 {
            background-color:  #f6faff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row21_col4 {
            background-color:  #fdb06e;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row21_col5 {
            background-color:  #2e964d;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row22_col0 {
            background-color:  #ffffff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row22_col1 {
            background-color:  #fff0e9;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row22_col2 {
            background-color:  #ebf7e7;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row22_col3 {
            background-color:  #f6faff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row22_col4 {
            background-color:  #f26c16;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row22_col5 {
            background-color:  #329b51;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row23_col0 {
            background-color:  #ffffff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row23_col1 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row23_col2 {
            background-color:  #eff9eb;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row23_col3 {
            background-color:  #f6faff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row23_col4 {
            background-color:  #feecd9;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row23_col5 {
            background-color:  #5db96b;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row24_col0 {
            background-color:  #ffffff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row24_col1 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row24_col2 {
            background-color:  #f6fcf4;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row24_col3 {
            background-color:  #f4f9fe;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row24_col4 {
            background-color:  #fff5eb;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row24_col5 {
            background-color:  #ecf8e8;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row25_col0 {
            background-color:  #ffffff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row25_col1 {
            background-color:  #fff4ef;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row25_col2 {
            background-color:  #f4fbf1;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row25_col3 {
            background-color:  #f5f9fe;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row25_col4 {
            background-color:  #fee5cb;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row25_col5 {
            background-color:  #cbebc5;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row26_col0 {
            background-color:  #ffffff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row26_col1 {
            background-color:  #fff4ee;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row26_col2 {
            background-color:  #e9f7e5;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row26_col3 {
            background-color:  #f7fbff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row26_col4 {
            background-color:  #fdd3a7;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row26_col5 {
            background-color:  #00682a;
            color:  #f1f1f1;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row27_col0 {
            background-color:  #ffffff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row27_col1 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row27_col2 {
            background-color:  #eff9eb;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row27_col3 {
            background-color:  #f6faff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row27_col4 {
            background-color:  #feebd7;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row27_col5 {
            background-color:  #55b567;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row28_col0 {
            background-color:  #ffffff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row28_col1 {
            background-color:  #fff4ef;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row28_col2 {
            background-color:  #f5fbf2;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row28_col3 {
            background-color:  #f5f9fe;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row28_col4 {
            background-color:  #fedcb9;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row28_col5 {
            background-color:  #d9f0d3;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row29_col0 {
            background-color:  #ffffff;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row29_col1 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row29_col2 {
            background-color:  #f5fbf3;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row29_col3 {
            background-color:  #f5f9fe;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row29_col4 {
            background-color:  #fff1e3;
            color:  #000000;
        }    #T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row29_col5 {
            background-color:  #dbf1d6;
            color:  #000000;
        }</style><table id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9" ><thead>    <tr>        <th class="blank level0" ></th>        <th class="col_heading level0 col0" >Confirmed</th>        <th class="col_heading level0 col1" >Deaths</th>        <th class="col_heading level0 col2" >Recovered</th>        <th class="col_heading level0 col3" >Active</th>        <th class="col_heading level0 col4" >Mortality Rate</th>        <th class="col_heading level0 col5" >Recovery Rate</th>    </tr>    <tr>        <th class="index_name level0" >Country/Region</th>        <th class="blank" ></th>        <th class="blank" ></th>        <th class="blank" ></th>        <th class="blank" ></th>        <th class="blank" ></th>        <th class="blank" ></th>    </tr></thead><tbody>
                <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row0" class="row_heading level0 row0" >US</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row0_col0" class="data row0 col0" >1039909</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row0_col1" class="data row0 col1" >60967</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row0_col2" class="data row0 col2" >120720</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row0_col3" class="data row0 col3" >858222</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row0_col4" class="data row0 col4" >5.860000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row0_col5" class="data row0 col5" >11.610000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row1" class="row_heading level0 row1" >Spain</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row1_col0" class="data row1 col0" >236899</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row1_col1" class="data row1 col1" >24275</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row1_col2" class="data row1 col2" >132929</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row1_col3" class="data row1 col3" >79695</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row1_col4" class="data row1 col4" >10.250000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row1_col5" class="data row1 col5" >56.110000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row2" class="row_heading level0 row2" >Italy</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row2_col0" class="data row2 col0" >203591</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row2_col1" class="data row2 col1" >27682</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row2_col2" class="data row2 col2" >71252</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row2_col3" class="data row2 col3" >104657</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row2_col4" class="data row2 col4" >13.600000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row2_col5" class="data row2 col5" >35.000000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row3" class="row_heading level0 row3" >France</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row3_col0" class="data row3 col0" >166543</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row3_col1" class="data row3 col1" >24121</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row3_col2" class="data row3 col2" >49118</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row3_col3" class="data row3 col3" >93304</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row3_col4" class="data row3 col4" >14.480000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row3_col5" class="data row3 col5" >29.490000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row4" class="row_heading level0 row4" >United Kingdom</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row4_col0" class="data row4 col0" >166441</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row4_col1" class="data row4 col1" >26166</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row4_col2" class="data row4 col2" >857</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row4_col3" class="data row4 col3" >139418</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row4_col4" class="data row4 col4" >15.720000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row4_col5" class="data row4 col5" >0.510000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row5" class="row_heading level0 row5" >Germany</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row5_col0" class="data row5 col0" >161539</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row5_col1" class="data row5 col1" >6467</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row5_col2" class="data row5 col2" >120400</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row5_col3" class="data row5 col3" >34672</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row5_col4" class="data row5 col4" >4.000000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row5_col5" class="data row5 col5" >74.530000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row6" class="row_heading level0 row6" >Turkey</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row6_col0" class="data row6 col0" >117589</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row6_col1" class="data row6 col1" >3081</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row6_col2" class="data row6 col2" >44040</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row6_col3" class="data row6 col3" >70468</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row6_col4" class="data row6 col4" >2.620000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row6_col5" class="data row6 col5" >37.450000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row7" class="row_heading level0 row7" >Russia</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row7_col0" class="data row7 col0" >99399</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row7_col1" class="data row7 col1" >972</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row7_col2" class="data row7 col2" >10286</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row7_col3" class="data row7 col3" >88141</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row7_col4" class="data row7 col4" >0.980000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row7_col5" class="data row7 col5" >10.350000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row8" class="row_heading level0 row8" >Iran</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row8_col0" class="data row8 col0" >93657</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row8_col1" class="data row8 col1" >5957</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row8_col2" class="data row8 col2" >73791</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row8_col3" class="data row8 col3" >13909</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row8_col4" class="data row8 col4" >6.360000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row8_col5" class="data row8 col5" >78.790000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row9" class="row_heading level0 row9" >China</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row9_col0" class="data row9 col0" >83944</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row9_col1" class="data row9 col1" >4637</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row9_col2" class="data row9 col2" >78474</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row9_col3" class="data row9 col3" >833</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row9_col4" class="data row9 col4" >5.520000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row9_col5" class="data row9 col5" >93.480000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row10" class="row_heading level0 row10" >Brazil</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row10_col0" class="data row10 col0" >79685</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row10_col1" class="data row10 col1" >5513</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row10_col2" class="data row10 col2" >34132</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row10_col3" class="data row10 col3" >40040</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row10_col4" class="data row10 col4" >6.920000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row10_col5" class="data row10 col5" >42.830000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row11" class="row_heading level0 row11" >Canada</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row11_col0" class="data row11 col0" >52865</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row11_col1" class="data row11 col1" >3155</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row11_col2" class="data row11 col2" >20327</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row11_col3" class="data row11 col3" >29383</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row11_col4" class="data row11 col4" >5.970000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row11_col5" class="data row11 col5" >38.450000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row12" class="row_heading level0 row12" >Belgium</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row12_col0" class="data row12 col0" >47859</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row12_col1" class="data row12 col1" >7501</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row12_col2" class="data row12 col2" >11283</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row12_col3" class="data row12 col3" >29075</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row12_col4" class="data row12 col4" >15.670000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row12_col5" class="data row12 col5" >23.580000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row13" class="row_heading level0 row13" >Netherlands</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row13_col0" class="data row13 col0" >38998</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row13_col1" class="data row13 col1" >4727</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row13_col2" class="data row13 col2" >119</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row13_col3" class="data row13 col3" >34152</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row13_col4" class="data row13 col4" >12.120000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row13_col5" class="data row13 col5" >0.310000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row14" class="row_heading level0 row14" >Peru</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row14_col0" class="data row14 col0" >33931</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row14_col1" class="data row14 col1" >943</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row14_col2" class="data row14 col2" >10037</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row14_col3" class="data row14 col3" >22951</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row14_col4" class="data row14 col4" >2.780000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row14_col5" class="data row14 col5" >29.580000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row15" class="row_heading level0 row15" >India</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row15_col0" class="data row15 col0" >33062</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row15_col1" class="data row15 col1" >1079</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row15_col2" class="data row15 col2" >8437</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row15_col3" class="data row15 col3" >23546</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row15_col4" class="data row15 col4" >3.260000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row15_col5" class="data row15 col5" >25.520000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row16" class="row_heading level0 row16" >Switzerland</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row16_col0" class="data row16 col0" >29407</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row16_col1" class="data row16 col1" >1716</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row16_col2" class="data row16 col2" >22600</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row16_col3" class="data row16 col3" >5091</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row16_col4" class="data row16 col4" >5.840000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row16_col5" class="data row16 col5" >76.850000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row17" class="row_heading level0 row17" >Ecuador</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row17_col0" class="data row17 col0" >24675</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row17_col1" class="data row17 col1" >883</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row17_col2" class="data row17 col2" >1557</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row17_col3" class="data row17 col3" >22235</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row17_col4" class="data row17 col4" >3.580000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row17_col5" class="data row17 col5" >6.310000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row18" class="row_heading level0 row18" >Portugal</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row18_col0" class="data row18 col0" >24505</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row18_col1" class="data row18 col1" >973</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row18_col2" class="data row18 col2" >1470</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row18_col3" class="data row18 col3" >22062</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row18_col4" class="data row18 col4" >3.970000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row18_col5" class="data row18 col5" >6.000000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row19" class="row_heading level0 row19" >Saudi Arabia</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row19_col0" class="data row19 col0" >21402</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row19_col1" class="data row19 col1" >157</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row19_col2" class="data row19 col2" >2953</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row19_col3" class="data row19 col3" >18292</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row19_col4" class="data row19 col4" >0.730000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row19_col5" class="data row19 col5" >13.800000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row20" class="row_heading level0 row20" >Sweden</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row20_col0" class="data row20 col0" >20302</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row20_col1" class="data row20 col1" >2462</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row20_col2" class="data row20 col2" >1005</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row20_col3" class="data row20 col3" >16835</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row20_col4" class="data row20 col4" >12.130000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row20_col5" class="data row20 col5" >4.950000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row21" class="row_heading level0 row21" >Ireland</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row21_col0" class="data row21 col0" >20253</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row21_col1" class="data row21 col1" >1190</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row21_col2" class="data row21 col2" >13386</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row21_col3" class="data row21 col3" >5677</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row21_col4" class="data row21 col4" >5.880000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row21_col5" class="data row21 col5" >66.090000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row22" class="row_heading level0 row22" >Mexico</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row22_col0" class="data row22 col0" >17799</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row22_col1" class="data row22 col1" >1732</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row22_col2" class="data row22 col2" >11423</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row22_col3" class="data row22 col3" >4644</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row22_col4" class="data row22 col4" >9.730000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row22_col5" class="data row22 col5" >64.180000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row23" class="row_heading level0 row23" >Israel</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row23_col0" class="data row23 col0" >15834</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row23_col1" class="data row23 col1" >215</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row23_col2" class="data row23 col2" >8233</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row23_col3" class="data row23 col3" >7386</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row23_col4" class="data row23 col4" >1.360000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row23_col5" class="data row23 col5" >52.000000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row24" class="row_heading level0 row24" >Singapore</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row24_col0" class="data row24 col0" >15641</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row24_col1" class="data row24 col1" >14</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row24_col2" class="data row24 col2" >1188</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row24_col3" class="data row24 col3" >14439</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row24_col4" class="data row24 col4" >0.090000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row24_col5" class="data row24 col5" >7.600000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row25" class="row_heading level0 row25" >Pakistan</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row25_col0" class="data row25 col0" >15525</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row25_col1" class="data row25 col1" >343</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row25_col2" class="data row25 col2" >3425</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row25_col3" class="data row25 col3" >11757</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row25_col4" class="data row25 col4" >2.210000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row25_col5" class="data row25 col5" >22.060000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row26" class="row_heading level0 row26" >Austria</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row26_col0" class="data row26 col0" >15402</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row26_col1" class="data row26 col1" >580</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row26_col2" class="data row26 col2" >12779</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row26_col3" class="data row26 col3" >2043</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row26_col4" class="data row26 col4" >3.770000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row26_col5" class="data row26 col5" >82.970000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row27" class="row_heading level0 row27" >Chile</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row27_col0" class="data row27 col0" >14885</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row27_col1" class="data row27 col1" >216</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row27_col2" class="data row27 col2" >8057</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row27_col3" class="data row27 col3" >6612</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row27_col4" class="data row27 col4" >1.450000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row27_col5" class="data row27 col5" >54.130000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row28" class="row_heading level0 row28" >Japan</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row28_col0" class="data row28 col0" >13895</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row28_col1" class="data row28 col1" >413</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row28_col2" class="data row28 col2" >2368</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row28_col3" class="data row28 col3" >11114</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row28_col4" class="data row28 col4" >2.970000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row28_col5" class="data row28 col5" >17.040000</td>
            </tr>
            <tr>
                        <th id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9level0_row29" class="row_heading level0 row29" >Belarus</th>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row29_col0" class="data row29 col0" >13181</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row29_col1" class="data row29 col1" >84</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row29_col2" class="data row29 col2" >2072</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row29_col3" class="data row29 col3" >11025</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row29_col4" class="data row29 col4" >0.640000</td>
                        <td id="T_24b852b6_8b42_11ea_8bd9_50e0853f99e9row29_col5" class="data row29 col5" >15.720000</td>
            </tr>
    </tbody></table>




<div>


            <div id="9d6826fd-11a8-4bdf-a03e-408ef5d49c79" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("9d6826fd-11a8-4bdf-a03e-408ef5d49c79")) {
                    Plotly.newPlot(
                        '9d6826fd-11a8-4bdf-a03e-408ef5d49c79',
                        [{"marker": {"color": "orange"}, "orientation": "h", "type": "bar", "x": [83944, 93657, 99399, 117589, 161539, 166441, 166543, 203591, 236899, 1039909], "y": ["China", "Iran", "Russia", "Turkey", "Germany", "United Kingdom", "France", "Italy", "Spain", "US"]}],
                        {"template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "Top 10 Confirmed Cases by Country"}, "xaxis": {"title": {"text": "Number of cases"}}, "yaxis": {"title": {"text": "Countries"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('9d6826fd-11a8-4bdf-a03e-408ef5d49c79');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="082336af-e5f4-45dd-85e1-5f85c9839dbd" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("082336af-e5f4-45dd-85e1-5f85c9839dbd")) {
                    Plotly.newPlot(
                        '082336af-e5f4-45dd-85e1-5f85c9839dbd',
                        [{"marker": {"color": "red"}, "orientation": "h", "type": "bar", "x": [4727, 5513, 5957, 6467, 7501, 24121, 24275, 26166, 27682, 60967], "y": ["Netherlands", "Brazil", "Iran", "Germany", "Belgium", "France", "Spain", "United Kingdom", "Italy", "US"]}],
                        {"template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "Top 10 Deaths by Country"}, "xaxis": {"title": {"text": "Number of cases"}}, "yaxis": {"title": {"text": "Countries"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('082336af-e5f4-45dd-85e1-5f85c9839dbd');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="7fd873c1-61ac-49e8-9256-cbe9c93cddb5" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("7fd873c1-61ac-49e8-9256-cbe9c93cddb5")) {
                    Plotly.newPlot(
                        '7fd873c1-61ac-49e8-9256-cbe9c93cddb5',
                        [{"marker": {"color": "green"}, "orientation": "h", "type": "bar", "x": [22600, 34132, 44040, 49118, 71252, 73791, 78474, 120400, 120720, 132929], "y": ["Switzerland", "Brazil", "Turkey", "France", "Italy", "Iran", "China", "Germany", "US", "Spain"]}],
                        {"template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "Top 10 Recovered Cases by Country"}, "xaxis": {"title": {"text": "Number of cases"}}, "yaxis": {"title": {"text": "Countries"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('7fd873c1-61ac-49e8-9256-cbe9c93cddb5');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>


<div id='Combined'></div>

<div><h2 style='display:inline'>Reported Cases, Deaths and Recoveries:</h2><a href='#Content' style='float:right; display:inline'>Return to Content</a></div>

***



<div>


            <div id="cafd5cc5-55da-4cdd-a3a7-2158bcaca1e5" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("cafd5cc5-55da-4cdd-a3a7-2158bcaca1e5")) {
                    Plotly.newPlot(
                        'cafd5cc5-55da-4cdd-a3a7-2158bcaca1e5',
                        [{"hovertemplate": " %{y:.0f}", "line": {"color": "orange"}, "mode": "lines", "name": "Cases", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [555, 654, 941, 1434, 2118, 2927, 5578, 6166, 8234, 9927, 12038, 16787, 19881, 23892, 27635, 30794, 34391, 37120, 40150, 42762, 44802, 45221, 60368, 66885, 69030, 71224, 73258, 75136, 75639, 76197, 76819, 78572, 78958, 79561, 80406, 81388, 82746, 84112, 86011, 88369, 90306, 92840, 95120, 97886, 101801, 105847, 109821, 113590, 118620, 125875, 128352, 145219, 156116, 167466, 181603, 197113, 214846, 242616, 272247, 304555, 337018, 378282, 418079, 467723, 529701, 593423, 660824, 720285, 782490, 857608, 932638, 1013458, 1095876, 1176059, 1249737, 1321427, 1396438, 1480200, 1565538, 1657929, 1736025, 1835164, 1905192, 1975581, 2055506, 2151872, 2239723, 2317339, 2400843, 2471759, 2548821, 2624107, 2707742, 2794829, 2879770, 2953368, 3021807, 3095043, 3169904]}, {"hovertemplate": " %{y:.0f}", "line": {"color": "red"}, "mode": "lines", "name": "Deaths", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [17, 18, 26, 42, 56, 82, 131, 133, 171, 213, 259, 362, 426, 492, 564, 634, 719, 806, 906, 1013, 1113, 1118, 1371, 1523, 1666, 1770, 1868, 2007, 2122, 2247, 2251, 2458, 2469, 2629, 2708, 2770, 2814, 2872, 2941, 2996, 3085, 3160, 3254, 3347, 3459, 3558, 3801, 3987, 4263, 4614, 4722, 5408, 5830, 6472, 7150, 7956, 8823, 9946, 11422, 13125, 14825, 16759, 19014, 21785, 24788, 28288, 31797, 35323, 39439, 44238, 49675, 55817, 61812, 67981, 73076, 78767, 86662, 93354, 100882, 108113, 114146, 119853, 125561, 132456, 140677, 147965, 156824, 163234, 167797, 173120, 180257, 186930, 193677, 200004, 206184, 209891, 214468, 220777, 227638]}, {"hovertemplate": " %{y:.0f}", "line": {"color": "green"}, "mode": "lines", "name": "Recovered", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [28, 30, 36, 39, 52, 61, 107, 126, 143, 222, 284, 472, 623, 852, 1124, 1487, 2011, 2616, 3244, 3946, 4683, 5150, 6295, 8058, 9395, 10865, 12583, 14352, 16121, 18177, 18890, 22886, 23394, 25227, 27905, 30384, 33277, 36711, 39782, 42716, 45602, 48228, 51170, 53796, 55865, 58358, 60694, 62494, 64404, 67003, 68324, 70251, 72624, 76034, 78088, 80840, 83312, 84975, 87420, 91692, 97899, 98351, 108000, 113787, 122150, 130915, 139415, 149082, 164566, 178034, 193177, 210263, 225796, 246152, 260012, 276515, 300054, 328661, 353975, 376096, 402110, 421722, 448655, 474261, 511019, 542107, 568343, 592319, 623903, 645905, 680390, 710502, 739409, 790081, 817838, 846378, 874010, 907303, 948737]}],
                        {"hovermode": "x unified", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "Combined World Sats"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Number of People"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('cafd5cc5-55da-4cdd-a3a7-2158bcaca1e5');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="c412a057-2059-4bab-bc43-40e1184ddce2" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("c412a057-2059-4bab-bc43-40e1184ddce2")) {
                    Plotly.newPlot(
                        'c412a057-2059-4bab-bc43-40e1184ddce2',
                        [{"hovertemplate": " %{y:.0f}", "line": {"color": "orange"}, "mode": "lines", "name": "Cases", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [1.0, 1.0, 2.0, 2.0, 5.0, 5.0, 5.0, 5.0, 5.0, 7.0, 8.0, 8.0, 11.0, 11.0, 11.0, 11.0, 11.0, 11.0, 11.0, 11.0, 12.0, 12.0, 13.0, 13.0, 13.0, 13.0, 13.0, 13.0, 13.0, 13.0, 15.0, 15.0, 15.0, 51.0, 51.0, 57.0, 58.0, 60.0, 68.0, 74.0, 98.0, 118.0, 149.0, 217.0, 262.0, 402.0, 518.0, 583.0, 959.0, 1281.0, 1663.0, 2179.0, 2727.0, 3499.0, 4632.0, 6421.0, 7783.0, 13747.0, 19273.0, 25600.0, 33276.0, 43843.0, 53736.0, 65778.0, 83836.0, 101657.0, 121465.0, 140909.0, 161831.0, 188172.0, 213242.0, 243622.0, 275367.0, 308650.0, 336802.0, 366317.0, 397121.0, 428654.0, 462780.0, 496535.0, 526396.0, 555313.0, 580619.0, 607670.0, 636350.0, 667592.0, 699706.0, 732197.0, 758809.0, 784326.0, 811865.0, 840351.0, 869170.0, 905358.0, 938154.0, 965785.0, 988197.0, 1012582.0, 1039909.0]}, {"hovertemplate": " %{y:.0f}", "line": {"color": "red"}, "mode": "lines", "name": "Deaths", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.0, 1.0, 6.0, 7.0, 11.0, 12.0, 14.0, 17.0, 21.0, 22.0, 28.0, 36.0, 41.0, 49.0, 58.0, 73.0, 99.0, 133.0, 164.0, 258.0, 349.0, 442.0, 586.0, 786.0, 1008.0, 1316.0, 1726.0, 2265.0, 2731.0, 3420.0, 4192.0, 5367.0, 6501.0, 7921.0, 9246.0, 10855.0, 12375.0, 13894.0, 16191.0, 18270.0, 20255.0, 22333.0, 24342.0, 26086.0, 27870.0, 30262.0, 32734.0, 34827.0, 37411.0, 39753.0, 40945.0, 42659.0, 45086.0, 47412.0, 49724.0, 51493.0, 53755.0, 54881.0, 56259.0, 58355.0, 60967.0]}, {"hovertemplate": " %{y:.0f}", "line": {"color": "green"}, "mode": "lines", "name": "Recovered", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 5.0, 5.0, 5.0, 5.0, 6.0, 6.0, 6.0, 7.0, 7.0, 7.0, 7.0, 7.0, 7.0, 7.0, 7.0, 7.0, 7.0, 7.0, 8.0, 8.0, 12.0, 12.0, 12.0, 12.0, 17.0, 17.0, 105.0, 121.0, 147.0, 176.0, 178.0, 178.0, 348.0, 361.0, 681.0, 869.0, 1072.0, 2665.0, 5644.0, 7024.0, 8474.0, 9001.0, 9707.0, 14652.0, 17448.0, 19581.0, 21763.0, 23559.0, 25410.0, 28790.0, 31270.0, 32988.0, 43482.0, 47763.0, 52096.0, 54703.0, 58545.0, 64840.0, 70337.0, 72329.0, 75204.0, 77366.0, 80203.0, 99079.0, 100372.0, 106988.0, 111424.0, 115936.0, 120720.0]}],
                        {"hovermode": "x unified", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "US Combined Stats"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Number of People"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('c412a057-2059-4bab-bc43-40e1184ddce2');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="5b355bda-21d7-47e0-96b6-e2e97e2d4ac2" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("5b355bda-21d7-47e0-96b6-e2e97e2d4ac2")) {
                    Plotly.newPlot(
                        '5b355bda-21d7-47e0-96b6-e2e97e2d4ac2',
                        [{"hovertemplate": " %{y:.0f}", "line": {"color": "orange"}, "mode": "lines", "name": "Cases", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [548.0, 643.0, 920.0, 1406.0, 2075.0, 2877.0, 5509.0, 6087.0, 8141.0, 9802.0, 11891.0, 16630.0, 19716.0, 23707.0, 27440.0, 30587.0, 34110.0, 36814.0, 39829.0, 42354.0, 44386.0, 44759.0, 59895.0, 66358.0, 68413.0, 70513.0, 72434.0, 74211.0, 74619.0, 75077.0, 75550.0, 77001.0, 77022.0, 77241.0, 77754.0, 78166.0, 78600.0, 78928.0, 79356.0, 79932.0, 80136.0, 80261.0, 80386.0, 80537.0, 80690.0, 80770.0, 80823.0, 80860.0, 80887.0, 80921.0, 80932.0, 80945.0, 80977.0, 81003.0, 81033.0, 81058.0, 81102.0, 81156.0, 81250.0, 81305.0, 81435.0, 81498.0, 81591.0, 81661.0, 81782.0, 81897.0, 81999.0, 82122.0, 82198.0, 82279.0, 82361.0, 82432.0, 82511.0, 82543.0, 82602.0, 82665.0, 82718.0, 82809.0, 82883.0, 82941.0, 83014.0, 83134.0, 83213.0, 83306.0, 83356.0, 83403.0, 83760.0, 83787.0, 83805.0, 83817.0, 83853.0, 83868.0, 83884.0, 83899.0, 83909.0, 83912.0, 83918.0, 83940.0, 83944.0]}, {"hovertemplate": " %{y:.0f}", "line": {"color": "red"}, "mode": "lines", "name": "Deaths", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [17.0, 18.0, 26.0, 42.0, 56.0, 82.0, 131.0, 133.0, 171.0, 213.0, 259.0, 361.0, 425.0, 491.0, 563.0, 633.0, 718.0, 805.0, 905.0, 1012.0, 1112.0, 1117.0, 1369.0, 1521.0, 1663.0, 1766.0, 1864.0, 2003.0, 2116.0, 2238.0, 2238.0, 2443.0, 2445.0, 2595.0, 2665.0, 2717.0, 2746.0, 2790.0, 2837.0, 2872.0, 2914.0, 2947.0, 2983.0, 3015.0, 3044.0, 3072.0, 3100.0, 3123.0, 3139.0, 3161.0, 3172.0, 3180.0, 3193.0, 3203.0, 3217.0, 3230.0, 3241.0, 3249.0, 3253.0, 3259.0, 3274.0, 3274.0, 3281.0, 3285.0, 3291.0, 3296.0, 3299.0, 3304.0, 3308.0, 3309.0, 3316.0, 3322.0, 3326.0, 3330.0, 3333.0, 3335.0, 3335.0, 3337.0, 3339.0, 3340.0, 3343.0, 3343.0, 3345.0, 3345.0, 3346.0, 3346.0, 4636.0, 4636.0, 4636.0, 4636.0, 4636.0, 4636.0, 4636.0, 4636.0, 4636.0, 4637.0, 4637.0, 4637.0, 4637.0]}, {"hovertemplate": " %{y:.0f}", "line": {"color": "green"}, "mode": "lines", "name": "Recovered", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [28.0, 30.0, 36.0, 39.0, 49.0, 58.0, 101.0, 120.0, 135.0, 214.0, 275.0, 463.0, 614.0, 843.0, 1115.0, 1477.0, 1999.0, 2596.0, 3219.0, 3918.0, 4636.0, 5082.0, 6217.0, 7977.0, 9298.0, 10755.0, 12462.0, 14206.0, 15962.0, 18014.0, 18704.0, 22699.0, 23187.0, 25015.0, 27676.0, 30084.0, 32930.0, 36329.0, 39320.0, 42162.0, 44854.0, 47450.0, 50001.0, 52292.0, 53944.0, 55539.0, 57388.0, 58804.0, 60181.0, 61644.0, 62901.0, 64196.0, 65660.0, 67017.0, 67910.0, 68798.0, 69755.0, 70535.0, 71266.0, 71857.0, 72362.0, 72814.0, 73280.0, 73773.0, 74181.0, 74720.0, 75100.0, 75582.0, 75923.0, 76206.0, 76405.0, 76565.0, 76760.0, 76946.0, 77207.0, 77310.0, 77410.0, 77567.0, 77679.0, 77791.0, 77877.0, 77956.0, 78039.0, 78200.0, 78311.0, 78401.0, 77552.0, 77614.0, 77690.0, 77745.0, 77799.0, 77861.0, 77983.0, 78109.0, 78175.0, 78277.0, 78374.0, 78422.0, 78474.0]}],
                        {"hovermode": "x unified", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "China Combined Stats"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Number of People"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('5b355bda-21d7-47e0-96b6-e2e97e2d4ac2');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="5ecc1859-3af8-43f8-a57d-1ea90501b896" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("5ecc1859-3af8-43f8-a57d-1ea90501b896")) {
                    Plotly.newPlot(
                        '5ecc1859-3af8-43f8-a57d-1ea90501b896',
                        [{"hovertemplate": " %{y:.0f}", "line": {"color": "orange"}, "mode": "lines", "name": "Cases", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 3.0, 20.0, 62.0, 155.0, 229.0, 322.0, 453.0, 655.0, 888.0, 1128.0, 1694.0, 2036.0, 2502.0, 3089.0, 3858.0, 4636.0, 5883.0, 7375.0, 9172.0, 10149.0, 12462.0, 12462.0, 17660.0, 21157.0, 24747.0, 27980.0, 31506.0, 35713.0, 41035.0, 47021.0, 53578.0, 59138.0, 63927.0, 69176.0, 74386.0, 80589.0, 86498.0, 92472.0, 97689.0, 101739.0, 105792.0, 110574.0, 115242.0, 119827.0, 124632.0, 128948.0, 132547.0, 135586.0, 139422.0, 143626.0, 147577.0, 152271.0, 156363.0, 159516.0, 162488.0, 165155.0, 168941.0, 172434.0, 175925.0, 178972.0, 181228.0, 183957.0, 187327.0, 189973.0, 192994.0, 195351.0, 197675.0, 199414.0, 201505.0, 203591.0]}, {"hovertemplate": " %{y:.0f}", "line": {"color": "red"}, "mode": "lines", "name": "Deaths", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.0, 2.0, 3.0, 7.0, 10.0, 12.0, 17.0, 21.0, 29.0, 34.0, 52.0, 79.0, 107.0, 148.0, 197.0, 233.0, 366.0, 463.0, 631.0, 827.0, 827.0, 1266.0, 1441.0, 1809.0, 2158.0, 2503.0, 2978.0, 3405.0, 4032.0, 4825.0, 5476.0, 6077.0, 6820.0, 7503.0, 8215.0, 9134.0, 10023.0, 10779.0, 11591.0, 12428.0, 13155.0, 13915.0, 14681.0, 15362.0, 15887.0, 16523.0, 17127.0, 17669.0, 18279.0, 18849.0, 19468.0, 19899.0, 20465.0, 21067.0, 21645.0, 22170.0, 22745.0, 23227.0, 23660.0, 24114.0, 24648.0, 25085.0, 25549.0, 25969.0, 26384.0, 26644.0, 26977.0, 27359.0, 27682.0]}, {"hovertemplate": " %{y:.0f}", "line": {"color": "green"}, "mode": "lines", "name": "Recovered", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.0, 2.0, 1.0, 1.0, 3.0, 45.0, 46.0, 46.0, 83.0, 149.0, 160.0, 276.0, 414.0, 523.0, 589.0, 622.0, 724.0, 724.0, 1045.0, 1045.0, 1439.0, 1966.0, 2335.0, 2749.0, 2941.0, 4025.0, 4440.0, 4440.0, 6072.0, 7024.0, 7024.0, 8326.0, 9362.0, 10361.0, 10950.0, 12384.0, 13030.0, 14620.0, 15729.0, 16847.0, 18278.0, 19758.0, 20996.0, 21815.0, 22837.0, 24392.0, 26491.0, 28470.0, 30455.0, 32534.0, 34211.0, 35435.0, 37130.0, 38092.0, 40164.0, 42727.0, 44927.0, 47055.0, 48877.0, 51600.0, 54543.0, 57576.0, 60498.0, 63120.0, 64928.0, 66624.0, 68941.0, 71252.0]}],
                        {"hovermode": "x unified", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "Italy Combined Stats"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Number of People"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('5ecc1859-3af8-43f8-a57d-1ea90501b896');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="2058fb07-706e-4a56-b19e-decdc93a620c" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("2058fb07-706e-4a56-b19e-decdc93a620c")) {
                    Plotly.newPlot(
                        '2058fb07-706e-4a56-b19e-decdc93a620c',
                        [{"hovertemplate": " %{y:.0f}", "line": {"color": "orange"}, "mode": "lines", "name": "Cases", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.0, 1.0, 1.0, 1.0, 1.0, 1.0, 1.0, 1.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 6.0, 13.0, 15.0, 32.0, 45.0, 84.0, 120.0, 165.0, 222.0, 259.0, 400.0, 500.0, 673.0, 1073.0, 1695.0, 2277.0, 2277.0, 5232.0, 6391.0, 7798.0, 9942.0, 11748.0, 13910.0, 17963.0, 20410.0, 25374.0, 28768.0, 35136.0, 39885.0, 49515.0, 57786.0, 65719.0, 73235.0, 80110.0, 87956.0, 95923.0, 104118.0, 112065.0, 119199.0, 126168.0, 131646.0, 136675.0, 141942.0, 148220.0, 153222.0, 158273.0, 163027.0, 166831.0, 170099.0, 172541.0, 177644.0, 184948.0, 190839.0, 191726.0, 198674.0, 200210.0, 204178.0, 208389.0, 213024.0, 202990.0, 205905.0, 207634.0, 209465.0, 210773.0, 212917.0]}, {"hovertemplate": " %{y:.0f}", "line": {"color": "red"}, "mode": "lines", "name": "Deaths", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.0, 2.0, 3.0, 5.0, 10.0, 17.0, 28.0, 35.0, 54.0, 55.0, 133.0, 195.0, 289.0, 342.0, 533.0, 623.0, 830.0, 1043.0, 1375.0, 1772.0, 2311.0, 2808.0, 3647.0, 4365.0, 5138.0, 5982.0, 6803.0, 7716.0, 8464.0, 9387.0, 10348.0, 11198.0, 11947.0, 12641.0, 13341.0, 14045.0, 14792.0, 15447.0, 16081.0, 16606.0, 17209.0, 17756.0, 18056.0, 18708.0, 19315.0, 20002.0, 20043.0, 20453.0, 20852.0, 21282.0, 21717.0, 22157.0, 22524.0, 22902.0, 23190.0, 23521.0, 23822.0, 24275.0]}, {"hovertemplate": " %{y:.0f}", "line": {"color": "green"}, "mode": "lines", "name": "Recovered", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 2.0, 30.0, 30.0, 32.0, 32.0, 183.0, 183.0, 193.0, 517.0, 517.0, 530.0, 1028.0, 1081.0, 1107.0, 1588.0, 2125.0, 2575.0, 2575.0, 3794.0, 5367.0, 7015.0, 9357.0, 12285.0, 14709.0, 16780.0, 19259.0, 22647.0, 26743.0, 30513.0, 34219.0, 38080.0, 40437.0, 43208.0, 48021.0, 52165.0, 55668.0, 59109.0, 62391.0, 64727.0, 67504.0, 70853.0, 74797.0, 74797.0, 74797.0, 77357.0, 80587.0, 82514.0, 85915.0, 89250.0, 92355.0, 95708.0, 98372.0, 100875.0, 102548.0, 108947.0]}],
                        {"hovermode": "x unified", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "Spain Combined Stats"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Number of People"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('2058fb07-706e-4a56-b19e-decdc93a620c');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="b3fdaed4-16eb-4f0e-a978-51794e4e5398" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("b3fdaed4-16eb-4f0e-a978-51794e4e5398")) {
                    Plotly.newPlot(
                        'b3fdaed4-16eb-4f0e-a978-51794e4e5398',
                        [{"hovertemplate": " %{y:.0f}", "line": {"color": "orange"}, "mode": "lines", "name": "Cases", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.0, 1.0, 5.0, 5.0, 11.0, 16.0, 22.0, 31.0, 49.0, 68.0, 103.0, 119.0, 177.0, 238.0, 251.0, 355.0, 425.0, 536.0, 634.0, 749.0, 901.0, 1051.0, 1221.0, 1389.0, 1638.0, 1862.0, 2055.0, 2311.0, 2554.0, 2946.0, 3383.0, 3627.0, 4102.0, 4413.0, 4848.0, 5205.0, 5575.0, 5955.0, 6356.0, 6674.0, 6934.0, 7202.0, 7582.0, 7918.0, 8379.0, 8742.0, 9287.0, 9593.0, 9856.0, 10169.0, 10511.0, 10892.0, 11273.0, 11617.0, 11902.0, 12218.0, 12640.0]}, {"hovertemplate": " %{y:.0f}", "line": {"color": "red"}, "mode": "lines", "name": "Deaths", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.0, 2.0, 3.0, 3.0, 4.0, 5.0, 5.0, 5.0, 5.0, 5.0, 7.0, 8.0, 10.0, 14.0, 16.0, 16.0, 18.0, 22.0, 31.0, 33.0, 43.0, 57.0, 71.0, 79.0, 94.0, 107.0, 129.0, 159.0, 174.0, 181.0, 208.0, 232.0, 245.0, 263.0, 286.0, 314.0, 332.0, 347.0, 360.0, 380.0, 401.0, 426.0, 454.0, 494.0, 524.0, 535.0, 562.0, 596.0, 624.0]}, {"hovertemplate": " %{y:.0f}", "line": {"color": "green"}, "mode": "lines", "name": "Recovered", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 13.0, 13.0, 13.0, 1.0, 1.0, 1.0, 1.0, 1.0, 1.0, 7.0, 7.0, 7.0, 7.0, 7.0, 7.0, 7.0, 47.0, 56.0, 56.0, 116.0, 134.0, 162.0, 191.0, 222.0, 284.0, 318.0, 375.0, 439.0, 487.0, 618.0, 668.0, 774.0, 866.0, 981.0, 1040.0, 1133.0, 1297.0, 1513.0, 1740.0, 1944.0, 2126.0, 2265.0, 2466.0, 2655.0, 3025.0]}],
                        {"hovermode": "x unified", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "Poland Combined Stats"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Number of People"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('b3fdaed4-16eb-4f0e-a978-51794e4e5398');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>


<div id='m_and_d_rates'></div>

<div><h2 style='display:inline'>Mortality and Recovery Rates:</h2><a href='#Content' style='float:right; display:inline'>Return to Content</a></div>

***


<div>


            <div id="ab9398e5-991c-423b-906f-bde333c93366" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("ab9398e5-991c-423b-906f-bde333c93366")) {
                    Plotly.newPlot(
                        'ab9398e5-991c-423b-906f-bde333c93366',
                        [{"hovertemplate": "%{y:.2f}%", "line": {"color": "red"}, "mode": "lines", "name": "Mortalitly Rate", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [3.063063063063063, 2.7522935779816518, 2.763018065887354, 2.928870292887029, 2.644003777148253, 2.801503245644004, 2.3485120114736464, 2.156989944858904, 2.0767549186300704, 2.1456633423995166, 2.1515201860774216, 2.1564305712753917, 2.142749358684171, 2.059266700150678, 2.0408901755020805, 2.0588426316814963, 2.0906632549213455, 2.1713362068965516, 2.25653798256538, 2.3689256816799964, 2.484264095352886, 2.472302691227527, 2.2710707659687253, 2.2770426852059504, 2.413443430392583, 2.485117376165338, 2.549892161948183, 2.6711563032367973, 2.805431060696202, 2.948934997440844, 2.9302646480688375, 3.128340884793565, 3.1269789001747768, 3.3043828006183933, 3.3679078675720717, 3.4034501400697894, 3.4007686172141254, 3.4144949591021496, 3.419330085686714, 3.390329187837364, 3.416162824175581, 3.4037052994398964, 3.4209419680403705, 3.4192836564983757, 3.3978055225390715, 3.3614556860373934, 3.461086677411424, 3.509992076767321, 3.593829033889732, 3.6655412115193644, 3.6789454001495887, 3.7240306020562044, 3.7344026236900767, 3.864665066341825, 3.9371596284202353, 4.0362634630897, 4.106662446589651, 4.099482309493191, 4.1954548626798465, 4.309566416575003, 4.39887483754577, 4.430292744566223, 4.547944288041255, 4.6576713140042285, 4.679621144759024, 4.766920055339952, 4.811719913320339, 4.9040310432675955, 5.040192206929162, 5.158300762119756, 5.326289514259551, 5.507579001793858, 5.6404191715121055, 5.780407275485328, 5.847310274081667, 5.960753034409014, 6.2059325226039395, 6.30685042561816, 6.443918959488687, 6.52096682065396, 6.575135726732046, 6.530914948200815, 6.5904643731445445, 6.704660553022124, 6.843910939690762, 6.8761060137405945, 7.001937293138481, 7.044027654132607, 6.9890867499457485, 7.003919071398141, 7.072171800216649, 7.1235662265296344, 7.1527124814698, 7.156215997472475, 7.159738451334655, 7.106835314799917, 7.09734274889164, 7.133244998534753, 7.181226939364725]}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "black", "dash": "dash"}, "mode": "lines", "name": "Mean", "type": "scatter", "y": [4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993, 4.232913020354993]}],
                        {"template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "World Mortality Rate"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Rate"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('ab9398e5-991c-423b-906f-bde333c93366');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="c0c79318-1def-48fd-91a1-194d6ac4a51a" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("c0c79318-1def-48fd-91a1-194d6ac4a51a")) {
                    Plotly.newPlot(
                        'c0c79318-1def-48fd-91a1-194d6ac4a51a',
                        [{"hovertemplate": "%{y:.2f}%", "line": {"color": "green"}, "mode": "lines", "name": "Recovery Rate", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [5.045045045045045, 4.587155963302752, 3.825717321997875, 2.7196652719665275, 2.4551463644948064, 2.0840450973693203, 1.9182502689135892, 2.0434641582873825, 1.7367014816614041, 2.23632517376851, 2.3591958797142385, 2.8116995293977483, 3.1336451888737993, 3.566047212456052, 4.067305952596345, 4.828862765473794, 5.847460091302957, 7.0474137931034475, 8.079701120797012, 9.227819091716945, 10.452658363465916, 11.388514185887088, 10.427710045056985, 12.047544292442252, 13.610024626973779, 15.254689430529037, 17.17628108875481, 19.10136286201022, 21.313079231613322, 23.855269892515455, 24.59027063617074, 29.127424527821617, 29.628410040781173, 31.707746257588514, 34.70512150834515, 37.332284857718584, 40.21584124912383, 43.645377591782385, 46.25222355280138, 48.33821815342485, 50.497198414280334, 51.94743644980612, 53.79520605550883, 54.95780806243998, 54.87667115254271, 55.13429761826032, 55.26629697416705, 55.01716700413769, 54.29438543247345, 53.22979145978153, 53.23173772126651, 48.375901225046306, 46.519254913013405, 45.40264889589529, 42.9992896593118, 41.01200834039358, 38.777542984277105, 35.02448313384113, 32.11054667269061, 30.10687724713106, 29.048596810852835, 25.999386700926824, 25.832438366911514, 24.32786072098229, 23.060179233190045, 22.06099190627933, 21.09714538212898, 20.697640517295238, 21.03106748968038, 20.759367916344065, 20.712966874607297, 20.747085720375193, 20.604155944650675, 20.930242445319493, 20.805337442998006, 20.92548434381922, 21.487097887625517, 22.20382380759357, 22.610438073045817, 22.68468673869629, 23.16268486916951, 22.98007153584094, 23.54907011996691, 24.006153126599212, 24.860983135052876, 25.19234415429914, 25.375593321138375, 25.560308612594014, 25.986830459134563, 26.131390641239697, 26.694302973806323, 27.07595383877258, 27.30721760049517, 28.269386069773855, 28.399420787076746, 28.658060898607964, 28.92342230989603, 29.314713882811965, 29.92951837027241]}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "black", "dash": "dash"}, "mode": "lines", "name": "Mean", "type": "scatter", "y": [25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336, 25.26637060215336]}],
                        {"template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "World Recovery Rate"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Rate"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('c0c79318-1def-48fd-91a1-194d6ac4a51a');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="2f0eb1ee-87c6-4cc0-a1a4-da0b716e33a1" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("2f0eb1ee-87c6-4cc0-a1a4-da0b716e33a1")) {
                    Plotly.newPlot(
                        '2f0eb1ee-87c6-4cc0-a1a4-da0b716e33a1',
                        [{"hovertemplate": "%{y:.2f}%", "line": {"color": "red"}, "mode": "lines", "name": "Mortality Rate", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "xaxis": "x", "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.4705882352941175, 1.3513513513513513, 6.122448979591836, 5.932203389830509, 7.38255033557047, 5.529953917050691, 5.343511450381679, 4.228855721393035, 4.054054054054054, 3.7735849056603774, 2.9197080291970803, 2.810304449648712, 2.4654239326518343, 2.248737953189537, 2.126879354602127, 2.0863103743926836, 2.1373056994818653, 2.071328453511914, 2.1071566234099963, 1.876773114133993, 1.8108234317438905, 1.7265625, 1.761028969828104, 1.7927605318979085, 1.8758374274229568, 2.000668916659065, 2.058781430411756, 2.228080702755344, 2.2483843082369406, 2.4270983400634454, 2.5903566065834114, 2.8521777947834956, 3.0486489528329317, 3.2513484003907696, 3.357700813823007, 3.5169285598574436, 3.6742655922470773, 3.792889764875777, 4.077094890474188, 4.262178820213972, 4.376809715199447, 4.497769542932523, 4.6242752604503075, 4.697530942009282, 4.800049602234856, 4.9800055951421, 5.144024514811032, 5.2168090690122115, 5.346674174581896, 5.429276547158757, 5.395956031096099, 5.438937380629993, 5.553386338861756, 5.6419281942902435, 5.720860130929507, 5.687584358894492, 5.7298695096967025, 5.682527684733144, 5.693095607454788, 5.762990059076697, 5.8627245268576385], "yaxis": "y"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "black", "dash": "dash"}, "mode": "lines", "name": "Mean", "type": "scatter", "xaxis": "x", "y": [2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877, 2.360360927934877], "yaxis": "y"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "green"}, "mode": "lines", "name": "Recovery Rate", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "xaxis": "x2", "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 27.27272727272727, 27.27272727272727, 25.0, 25.0, 23.076923076923077, 23.076923076923077, 23.076923076923077, 23.076923076923077, 23.076923076923077, 23.076923076923077, 23.076923076923077, 23.076923076923077, 33.33333333333333, 33.33333333333333, 33.33333333333333, 9.803921568627452, 11.76470588235294, 10.526315789473683, 10.344827586206897, 11.666666666666666, 10.294117647058822, 9.45945945945946, 7.142857142857142, 5.932203389830509, 4.697986577181208, 3.225806451612903, 2.6717557251908395, 1.7412935323383085, 1.3513513513513513, 1.2006861063464835, 0.8342022940563086, 0.624512099921936, 0.7215874924834637, 0.5507113354749885, 0.44004400440044, 0.3429551300371535, 0.36701208981001726, 0.264756268494004, 1.3490941796222538, 0.880192041900051, 0.7627250557775126, 0.6875, 0.5349200625075129, 0.40599411536619306, 0.6476105404198302, 0.5488157134604276, 0.8123002051624602, 0.8548353777900194, 0.8825587617832297, 1.8912915427687373, 3.487588904474421, 3.7327551389154605, 3.9738888211515553, 3.6946581179039657, 3.525113757276652, 4.747124574761056, 5.1804918023052124, 5.345370266736187, 5.480193694113381, 5.496041096082155, 5.490729936470894, 5.798181397081777, 5.940394683850181, 5.940433593306837, 7.488904083400646, 7.860022709694406, 8.186689714779602, 8.19407662164915, 8.367085604525329, 8.85554024395074, 9.269394538019448, 9.221803178780252, 9.263116404820998, 9.206391138940752, 9.22753891643752, 10.94362672003782, 10.69888312579811, 11.077827880946588, 11.275484544073702, 11.449541864263832, 11.608708069648403], "yaxis": "y2"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "black", "dash": "dash"}, "mode": "lines", "name": "Mean", "type": "scatter", "xaxis": "x2", "y": [7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563, 7.42844458073563], "yaxis": "y2"}],
                        {"annotations": [{"font": {"size": 16}, "showarrow": false, "text": "US Mortality Rate", "x": 0.225, "xanchor": "center", "xref": "paper", "y": 1.0, "yanchor": "bottom", "yref": "paper"}, {"font": {"size": 16}, "showarrow": false, "text": "US Recovery Rate", "x": 0.775, "xanchor": "center", "xref": "paper", "y": 1.0, "yanchor": "bottom", "yref": "paper"}], "hovermode": "x", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "xaxis": {"anchor": "y", "domain": [0.0, 0.45], "title": {"text": "Days since 1/22/20"}}, "xaxis2": {"anchor": "y2", "domain": [0.55, 1.0], "title": {"text": "Days since 1/22/20"}}, "yaxis": {"anchor": "x", "domain": [0.0, 1.0], "title": {"text": "Percent"}}, "yaxis2": {"anchor": "x2", "domain": [0.0, 1.0], "title": {"text": "Percent"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('2f0eb1ee-87c6-4cc0-a1a4-da0b716e33a1');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="13f897be-541f-4f46-835a-becc4cf78da1" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("13f897be-541f-4f46-835a-becc4cf78da1")) {
                    Plotly.newPlot(
                        '13f897be-541f-4f46-835a-becc4cf78da1',
                        [{"hovertemplate": "%{y:.2f}%", "line": {"color": "red"}, "mode": "lines", "name": "Mortality Rate", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "xaxis": "x", "y": [3.102189781021898, 2.7993779160186625, 2.8260869565217392, 2.987197724039829, 2.6987951807228914, 2.8501911713590546, 2.3779270284988203, 2.1849843929686217, 2.10047905662695, 2.1730259130789635, 2.178117904297368, 2.1707757065544198, 2.155609657131264, 2.0711182351204287, 2.051749271137026, 2.0695066531533004, 2.1049545587804164, 2.186668115390884, 2.2722137136257503, 2.389384709826699, 2.505294462217816, 2.4955874796130386, 2.2856665831872442, 2.2921124807860394, 2.430824550889451, 2.5045027158112685, 2.57337714333048, 2.699060786136826, 2.835738886878677, 2.980939568709458, 2.9622766379880874, 3.172686069012091, 3.1744176988392927, 3.359614712393677, 3.427476399927978, 3.4759358288770055, 3.493638676844784, 3.5348672207581595, 3.5750289833156916, 3.593054095981584, 3.6363182589597685, 3.6717708476096735, 3.710845172044883, 3.743620944410644, 3.7724625108439707, 3.803392348644299, 3.8355418630835283, 3.8622310165718527, 3.8807224893987904, 3.9062789634334725, 3.9193396925814263, 3.928593489406387, 3.9430949528878574, 3.954174536745553, 3.969987535942147, 3.9848010066865704, 3.996202313136544, 4.003400857607571, 4.003692307692307, 4.008363569276182, 4.020384355621047, 4.017276497582762, 4.021276856516037, 4.022728107664614, 4.024112885476021, 4.024567444472935, 4.0232197953633575, 4.023282433452668, 4.0244288182194214, 4.021682324773028, 4.026177438350675, 4.029988354037267, 4.030977687823442, 4.0342609306664405, 4.035011258807293, 4.034355531361519, 4.031770594066588, 4.029755219843254, 4.0285703944114, 4.026958922607637, 4.02703158503385, 4.021218755262588, 4.01980459783928, 4.015317023983867, 4.014108162579778, 4.01184609666319, 5.534861509073544, 5.533077923782926, 5.531889505399439, 5.53109751005166, 5.528722884094785, 5.527734058282062, 5.526679700538839, 5.525691605382662, 5.525033071541789, 5.526027266660311, 5.525632164732238, 5.524183940910174, 5.523920709044124], "yaxis": "y"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "black", "dash": "dash"}, "mode": "lines", "name": "Mean", "type": "scatter", "xaxis": "x", "y": [3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115, 3.6481005376395115], "yaxis": "y"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "green"}, "mode": "lines", "name": "Recovery Rate", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "xaxis": "x2", "y": [5.109489051094891, 4.665629860031104, 3.91304347826087, 2.7738264580369845, 2.36144578313253, 2.0159888773027457, 1.8333635868578688, 1.9714144898965007, 1.658272939442329, 2.1832279126708833, 2.3126734505087883, 2.7841250751653637, 3.114221951714344, 3.5559117560214286, 4.063411078717201, 4.828848857357701, 5.860451480504251, 7.051665127397186, 8.082050767029049, 9.250602068281626, 10.44473482629658, 11.35414106660113, 10.379831371566908, 12.021157961361101, 13.590984169675355, 15.252506629983124, 17.204627661043155, 19.14271469189204, 21.39133464667176, 23.994032792999185, 24.757114493712773, 29.47883793716965, 30.10438575991275, 32.385650108103206, 35.59431026056537, 38.48732185349129, 41.895674300254456, 46.02802554226637, 49.54886839054387, 52.74733523494971, 55.972347010082856, 59.119622232466575, 62.20112954992163, 64.92916299340675, 66.85338951542941, 68.76191655317568, 71.00454078665727, 72.72322532772694, 74.40132530567335, 76.17800076617937, 77.72080264913754, 79.30817221570202, 81.08475246057523, 82.73397281582163, 83.80536324707218, 84.87502775790175, 86.00897635076818, 86.91285918477993, 87.712, 88.37955845273969, 88.85859888254436, 89.3445237919949, 89.81382750548468, 90.34055424253927, 90.70577877772615, 91.23655323149809, 91.5864827619849, 92.03623876671294, 92.3659943064308, 92.61901578774658, 92.76842194728087, 92.88261840062113, 93.0300202397256, 93.21929176308106, 93.46868114573496, 93.52204681545999, 93.58301699750962, 93.66977019406103, 93.72126974168407, 93.79076693070978, 93.8118871515648, 93.77150143142397, 93.78222152788626, 93.87078961899503, 93.94764624022265, 94.00261381485079, 92.5883476599809, 92.63250862305608, 92.70329932581588, 92.75564622928523, 92.78022253228865, 92.83755425191968, 92.96528539411568, 93.09884503986937, 93.16640646414568, 93.2846315187339, 93.39355084725565, 93.42625685013105, 93.48375107214333], "yaxis": "y2"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "black", "dash": "dash"}, "mode": "lines", "name": "Mean", "type": "scatter", "xaxis": "x2", "y": [57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224, 57.9873316843224], "yaxis": "y2"}],
                        {"annotations": [{"font": {"size": 16}, "showarrow": false, "text": "China Mortality Rate", "x": 0.225, "xanchor": "center", "xref": "paper", "y": 1.0, "yanchor": "bottom", "yref": "paper"}, {"font": {"size": 16}, "showarrow": false, "text": "China Recovery Rate", "x": 0.775, "xanchor": "center", "xref": "paper", "y": 1.0, "yanchor": "bottom", "yref": "paper"}], "hovermode": "x", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "xaxis": {"anchor": "y", "domain": [0.0, 0.45], "title": {"text": "Days since 1/22/20"}}, "xaxis2": {"anchor": "y2", "domain": [0.55, 1.0], "title": {"text": "Days since 1/22/20"}}, "yaxis": {"anchor": "x", "domain": [0.0, 1.0], "title": {"text": "Percent"}}, "yaxis2": {"anchor": "x2", "domain": [0.0, 1.0], "title": {"text": "Percent"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('13f897be-541f-4f46-835a-becc4cf78da1');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="a28fa25a-2fa2-4ffb-9277-af9bac4ed37d" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("a28fa25a-2fa2-4ffb-9277-af9bac4ed37d")) {
                    Plotly.newPlot(
                        'a28fa25a-2fa2-4ffb-9277-af9bac4ed37d',
                        [{"hovertemplate": "%{y:.2f}%", "line": {"color": "red"}, "mode": "lines", "name": "Mortality Rate", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "xaxis": "x", "y": [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 5.0, 3.225806451612903, 1.935483870967742, 3.056768558951965, 3.1055900621118013, 2.6490066225165565, 2.595419847328244, 2.364864864864865, 2.5709219858156027, 2.0070838252656436, 2.5540275049115913, 3.1574740207833734, 3.463904176108773, 3.8361845515811304, 4.249352890422778, 3.960564337922828, 4.96271186440678, 5.04797208896642, 6.21736131638585, 6.636173968865351, 6.636173968865351, 7.168742921857304, 6.810984544122513, 7.309976966905079, 7.71265189421015, 7.9445185044118585, 8.338700193206956, 8.29779456561472, 8.574892069500862, 9.00556198439658, 9.259697656329264, 9.506155458569932, 9.858910604834046, 10.086575430860647, 10.193698891908324, 10.559781729057319, 10.838956657150273, 11.03399563922243, 11.392877854116907, 11.747580157289777, 11.897010147050842, 12.074590860970828, 12.25182972118137, 12.325887412542526, 12.320470267084406, 12.465766860057187, 12.631835145221485, 12.673035819311156, 12.726804339047249, 12.772315469212684, 12.785100248898345, 12.726156443659944, 12.829434037964843, 12.965265127270936, 13.105870243104961, 13.12292457130004, 13.19055406706334, 13.202785277817252, 13.219945019332632, 13.305890921932592, 13.398783411340695, 13.39102211640607, 13.448753243882026, 13.455858731359523, 13.505945707982042, 13.478689768559505, 13.528137442707134, 13.577330587330339, 13.596868230913941], "yaxis": "y"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "black", "dash": "dash"}, "mode": "lines", "name": "Mean", "type": "scatter", "xaxis": "x", "y": [6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095, 6.372219815583095], "yaxis": "y"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "green"}, "mode": "lines", "name": "Recovery Rate", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "xaxis": "x2", "y": [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.6129032258064515, 1.2903225806451613, 0.43668122270742354, 0.3105590062111801, 0.6622516556291391, 6.870229007633588, 5.18018018018018, 4.078014184397164, 4.899645808736717, 7.318271119842828, 6.394884092725819, 8.934930398187117, 10.730948678071538, 11.281276962899051, 10.011898691143974, 8.433898305084746, 7.893589184474488, 7.133707754458567, 8.3854918953619, 8.3854918953619, 8.148357870894678, 9.292432764569645, 9.435487129753103, 9.824874910650465, 9.334729892718848, 11.270405734606447, 10.820031680272937, 9.44258948129559, 11.333009817462392, 11.877303933173256, 10.987532654433965, 12.035966231062796, 12.585701610518107, 12.856593331596123, 12.659252237045942, 13.392161951725928, 13.338246885524471, 14.37010389329559, 14.86785390199637, 15.23595058512851, 15.8605369570122, 16.488771311974766, 16.846395789203413, 16.917672239972703, 17.229360151493434, 17.990057970586935, 19.00058814247393, 19.822316293707267, 20.636684578220184, 21.365854299242798, 21.87921695030154, 22.214072569522806, 22.85091822165329, 23.06439405407042, 23.77398026529972, 24.778755929805026, 25.537587039931793, 26.291822184475784, 26.969894276822565, 28.05003343172589, 29.1164647915143, 30.307464744990074, 31.34708851052364, 32.31107084171568, 32.8458328063741, 33.40989098057308, 34.213046822659486, 34.9976177728878], "yaxis": "y2"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "black", "dash": "dash"}, "mode": "lines", "name": "Mean", "type": "scatter", "xaxis": "x2", "y": [10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675, 10.499708608848675], "yaxis": "y2"}],
                        {"annotations": [{"font": {"size": 16}, "showarrow": false, "text": "Italy Mortality Rate", "x": 0.225, "xanchor": "center", "xref": "paper", "y": 1.0, "yanchor": "bottom", "yref": "paper"}, {"font": {"size": 16}, "showarrow": false, "text": "Italy Recovery Rate", "x": 0.775, "xanchor": "center", "xref": "paper", "y": 1.0, "yanchor": "bottom", "yref": "paper"}], "hovermode": "x", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "xaxis": {"anchor": "y", "domain": [0.0, 0.45], "title": {"text": "Days since 1/22/20"}}, "xaxis2": {"anchor": "y2", "domain": [0.55, 1.0], "title": {"text": "Days since 1/22/20"}}, "yaxis": {"anchor": "x", "domain": [0.0, 1.0], "title": {"text": "Percent"}}, "yaxis2": {"anchor": "x2", "domain": [0.0, 1.0], "title": {"text": "Percent"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('a28fa25a-2fa2-4ffb-9277-af9bac4ed37d');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="00fd05d1-dc86-48de-a82b-aabc34e5fc3a" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("00fd05d1-dc86-48de-a82b-aabc34e5fc3a")) {
                    Plotly.newPlot(
                        '00fd05d1-dc86-48de-a82b-aabc34e5fc3a',
                        [{"hovertemplate": "%{y:.2f}%", "line": {"color": "red"}, "mode": "lines", "name": "Mortality Rate", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "xaxis": "x", "y": [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.6060606060606061, 0.9009009009009009, 1.1583011583011582, 1.25, 2.0, 2.526002971768202, 2.60950605778192, 2.0648967551622417, 2.371541501976284, 2.4154589371980677, 2.5420489296636086, 3.0511657017681113, 3.7060784816619647, 3.4399517199758605, 4.536942458290773, 4.478792235801582, 4.620609029672104, 5.110240078392945, 5.418932765823284, 6.159621802002225, 6.577299635701276, 7.04024069198947, 7.365444814702615, 7.553732738033434, 7.818134785982744, 8.168225575203113, 8.49207339907627, 8.772568102232935, 8.823744044702522, 9.015732150060508, 9.233926738946147, 9.394374113876793, 9.46912053769577, 9.602266684897376, 9.76111212730931, 9.894886643840442, 9.979759816489004, 10.081450444453147, 10.16029265888686, 10.186042802725929, 10.315229184024552, 10.438626917265829, 10.464759100735478, 10.5311747089685, 10.443476004066007, 10.48108615115359, 10.453981202340842, 10.294754220481794, 10.41506418260826, 10.423258137507469, 10.421375408490851, 10.401175454408893, 11.096113109020148, 11.122605084869235, 11.16869106215745, 11.229083617788174, 11.302206639370317, 11.40115631912905], "yaxis": "y"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "black", "dash": "dash"}, "mode": "lines", "name": "Mean", "type": "scatter", "xaxis": "x", "y": [4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595, 4.351124213165595], "yaxis": "y"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "green"}, "mode": "lines", "name": "Recovery Rate", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "xaxis": "x2", "y": [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 100.0, 100.0, 100.0, 100.0, 100.0, 100.0, 100.0, 100.0, 100.0, 100.0, 33.33333333333333, 15.384615384615385, 13.333333333333334, 6.25, 4.444444444444445, 2.380952380952381, 1.6666666666666667, 1.2121212121212122, 0.9009009009009009, 0.7722007722007722, 0.5, 6.0, 4.457652303120357, 2.982292637465051, 1.887905604719764, 8.036890645586297, 8.036890645586297, 3.688837920489297, 8.089500860585199, 6.629905103872788, 5.330919332126332, 8.750425604358188, 7.771387491013659, 6.162667705839782, 7.780499755022048, 8.374714274454167, 8.950917686318132, 7.328665755919854, 9.512348000501442, 10.839139654650106, 12.139618592738726, 14.237891629513536, 16.77476616371953, 18.36100362002247, 19.07772067852108, 20.077562211357026, 21.75128219904339, 23.863829027796367, 25.598369113834845, 27.12177414241329, 28.926059280190813, 29.586244741174315, 30.440602499612517, 32.398461746053165, 34.04537207450627, 35.172139278335536, 36.2571843927693, 37.397725842319474, 38.052545870346094, 39.12345471511119, 39.88482583143816, 40.442178342020455, 39.193770665325225, 39.012444843161596, 38.936649989429924, 40.25123620198791, 40.41277708665968, 41.228183829280816, 41.896687697160885, 45.49731513867678, 46.48162987785629, 47.377597118005724, 48.15840355190605, 48.6532905068486, 51.168765293518135], "yaxis": "y2"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "black", "dash": "dash"}, "mode": "lines", "name": "Mean", "type": "scatter", "xaxis": "x2", "y": [24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915, 24.240297911139915], "yaxis": "y2"}],
                        {"annotations": [{"font": {"size": 16}, "showarrow": false, "text": "Spain Mortality Rate", "x": 0.225, "xanchor": "center", "xref": "paper", "y": 1.0, "yanchor": "bottom", "yref": "paper"}, {"font": {"size": 16}, "showarrow": false, "text": "Spain Recovery Rate", "x": 0.775, "xanchor": "center", "xref": "paper", "y": 1.0, "yanchor": "bottom", "yref": "paper"}], "hovermode": "x", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "xaxis": {"anchor": "y", "domain": [0.0, 0.45], "title": {"text": "Days since 1/22/20"}}, "xaxis2": {"anchor": "y2", "domain": [0.55, 1.0], "title": {"text": "Days since 1/22/20"}}, "yaxis": {"anchor": "x", "domain": [0.0, 1.0], "title": {"text": "Percent"}}, "yaxis2": {"anchor": "x2", "domain": [0.0, 1.0], "title": {"text": "Percent"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('00fd05d1-dc86-48de-a82b-aabc34e5fc3a');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="eda77cc1-35aa-467f-a835-5a13b9d676ba" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("eda77cc1-35aa-467f-a835-5a13b9d676ba")) {
                    Plotly.newPlot(
                        'eda77cc1-35aa-467f-a835-5a13b9d676ba',
                        [{"hovertemplate": "%{y:.2f}%", "line": {"color": "red"}, "mode": "lines", "name": "Mortality Rate", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "xaxis": "x", "y": [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 1.508515815085158, 1.4279532669839896, 1.6836335160532498, 1.9348268839103868, 2.0987289388117056, 2.178108629721533, 2.2915650901999025, 2.4246544300929074, 2.660891089108911, 3.054755043227666, 3.1210762331838566, 3.0394626364399664, 3.2724984266834483, 3.4761762061732093, 3.533314104413037, 3.6517633990558176, 3.772091796359799, 3.965647890881536, 3.9622866690535865, 3.969343399679707, 3.876386346505868, 3.9612217241738765, 4.068587662337662, 4.189202478119776, 4.3192845590333935, 4.535438854204921, 4.648274638516811, 4.605319789962985, 4.721895479751302, 4.878048780487805, 4.936708860759493], "yaxis": "y"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "black", "dash": "dash"}, "mode": "lines", "name": "Mean", "type": "scatter", "xaxis": "x", "y": [1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975, 1.0683602286764975], "yaxis": "y"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "green"}, "mode": "lines", "name": "Recovery Rate", "type": "scatter", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "xaxis": "x2", "y": [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0.34063260340632606, 0.3028991778450887, 1.8402505873140171, 1.9008825526137134, 1.6553355010345847, 3.198235456299973, 3.266699171136031, 3.6709721278042147, 3.93976897689769, 4.265129682997118, 5.0941704035874436, 5.3400503778337525, 5.899937067337949, 6.577764459094995, 7.023363138159793, 8.580949736184392, 8.810340279609601, 9.775195756504168, 10.335362215061464, 11.22168840082361, 11.198449445461398, 11.810695298655268, 13.159496753246753, 14.878552463369063, 16.554086195414328, 17.8479618068307, 18.859221147875456, 19.497288456572264, 20.719206855990592, 21.7302340808643, 23.931962025316455], "yaxis": "y2"}, {"hovertemplate": "%{y:.2f}%", "line": {"color": "black", "dash": "dash"}, "mode": "lines", "name": "Mean", "type": "scatter", "xaxis": "x2", "y": [2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294, 2.9618866889004294], "yaxis": "y2"}],
                        {"annotations": [{"font": {"size": 16}, "showarrow": false, "text": "Ploand Mortality Rate", "x": 0.225, "xanchor": "center", "xref": "paper", "y": 1.0, "yanchor": "bottom", "yref": "paper"}, {"font": {"size": 16}, "showarrow": false, "text": "Ploand Recovery Rate", "x": 0.775, "xanchor": "center", "xref": "paper", "y": 1.0, "yanchor": "bottom", "yref": "paper"}], "hovermode": "x", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "xaxis": {"anchor": "y", "domain": [0.0, 0.45], "title": {"text": "Days since 1/22/20"}}, "xaxis2": {"anchor": "y2", "domain": [0.55, 1.0], "title": {"text": "Days since 1/22/20"}}, "yaxis": {"anchor": "x", "domain": [0.0, 1.0], "title": {"text": "Percent"}}, "yaxis2": {"anchor": "x2", "domain": [0.0, 1.0], "title": {"text": "Percent"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('eda77cc1-35aa-467f-a835-5a13b9d676ba');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>


<div id='daily_increase'></div>

<div><h2 style='display:inline'>Daily Increases:</h2><a href='#Content' style='float:right; display:inline'>Return to Content</a></div>

***


<div>


            <div id="c2dbd807-c89c-412e-9c83-597ca9451ffb" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("c2dbd807-c89c-412e-9c83-597ca9451ffb")) {
                    Plotly.newPlot(
                        'c2dbd807-c89c-412e-9c83-597ca9451ffb',
                        [{"hovertemplate": " %{y:.0f}", "marker": {"color": "orange"}, "name": "Cases", "type": "bar", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [555, 99, 287, 493, 684, 809, 2651, 588, 2068, 1693, 2111, 4749, 3094, 4011, 3743, 3159, 3597, 2729, 3030, 2612, 2040, 419, 15147, 6517, 2145, 2194, 2034, 1878, 503, 558, 622, 1753, 386, 603, 845, 982, 1358, 1366, 1899, 2358, 1937, 2534, 2280, 2766, 3915, 4046, 3974, 3769, 5030, 7255, 2477, 16867, 10897, 11350, 14137, 15510, 17733, 27770, 29631, 32308, 32463, 41264, 39797, 49644, 61978, 63722, 67401, 59461, 62205, 75118, 75030, 80820, 82418, 80183, 73678, 71690, 75011, 83762, 85338, 92391, 78096, 99139, 70028, 70389, 79925, 96366, 87851, 77616, 83504, 70916, 77062, 75286, 83635, 87087, 84941, 73598, 68439, 73236, 74861]}],
                        {"hovermode": "x unified", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "World Daily Case Increase:"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Number of People"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('c2dbd807-c89c-412e-9c83-597ca9451ffb');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="6a536171-e50a-4787-87ba-44f405613cd2" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("6a536171-e50a-4787-87ba-44f405613cd2")) {
                    Plotly.newPlot(
                        '6a536171-e50a-4787-87ba-44f405613cd2',
                        [{"hovertemplate": " %{y:.0f}", "marker": {"color": "red"}, "name": "Deaths", "type": "bar", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [17, 1, 8, 16, 14, 26, 49, 2, 38, 42, 46, 103, 64, 66, 72, 70, 85, 87, 100, 107, 100, 5, 253, 152, 143, 104, 98, 139, 115, 125, 4, 207, 11, 160, 79, 62, 44, 58, 69, 55, 89, 75, 94, 93, 112, 99, 243, 186, 276, 351, 108, 686, 422, 642, 678, 806, 867, 1123, 1476, 1703, 1700, 1934, 2255, 2771, 3003, 3500, 3509, 3526, 4116, 4799, 5437, 6142, 5995, 6169, 5095, 5691, 7895, 6692, 7528, 7231, 6033, 5707, 5708, 6895, 8221, 7288, 8859, 6410, 4563, 5323, 7137, 6673, 6747, 6327, 6180, 3707, 4577, 6309, 6861]}],
                        {"hovermode": "x unified", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "World Daily Increase in Deaths:"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Number of People"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('6a536171-e50a-4787-87ba-44f405613cd2');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="d39875ad-079f-4ff7-85d0-ae8d0d644b1e" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("d39875ad-079f-4ff7-85d0-ae8d0d644b1e")) {
                    Plotly.newPlot(
                        'd39875ad-079f-4ff7-85d0-ae8d0d644b1e',
                        [{"hovertemplate": " %{y:.0f}", "marker": {"color": "green"}, "name": "Recovered", "type": "bar", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [28, 2, 6, 3, 13, 9, 46, 19, 17, 79, 62, 188, 151, 229, 272, 363, 524, 605, 628, 702, 737, 467, 1145, 1763, 1337, 1470, 1718, 1769, 1769, 2056, 713, 3996, 508, 1833, 2678, 2479, 2893, 3434, 3071, 2934, 2886, 2626, 2942, 2626, 2069, 2493, 2336, 1800, 1910, 2599, 1321, 1927, 2373, 3410, 2054, 2752, 2472, 1663, 2445, 4272, 6207, 452, 9649, 5787, 8363, 8765, 8500, 9667, 15484, 13468, 15143, 17086, 15533, 20356, 13860, 16503, 23539, 28607, 25314, 22121, 26014, 19612, 26933, 25606, 36758, 31088, 26236, 23976, 31584, 22002, 34485, 30112, 28907, 50672, 27757, 28540, 27632, 33293, 41434]}],
                        {"hovermode": "x unified", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "World Daily Increase in Recoveries:"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Number of People"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('d39875ad-079f-4ff7-85d0-ae8d0d644b1e');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="61d0bb46-ca4a-411b-a6cb-4f0b264ff3b2" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("61d0bb46-ca4a-411b-a6cb-4f0b264ff3b2")) {
                    Plotly.newPlot(
                        '61d0bb46-ca4a-411b-a6cb-4f0b264ff3b2',
                        [{"hovertemplate": " %{y:.0f}", "marker": {"color": "orange"}, "name": "Cases:", "type": "bar", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [1.0, 0.0, 1.0, 0.0, 3.0, 0.0, 0.0, 0.0, 0.0, 2.0, 1.0, 0.0, 3.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 2.0, 0.0, 0.0, 36.0, 0.0, 6.0, 1.0, 2.0, 8.0, 6.0, 24.0, 20.0, 31.0, 68.0, 45.0, 140.0, 116.0, 65.0, 376.0, 322.0, 382.0, 516.0, 548.0, 772.0, 1133.0, 1789.0, 1362.0, 5964.0, 5526.0, 6327.0, 7676.0, 10567.0, 9893.0, 12042.0, 18058.0, 17821.0, 19808.0, 19444.0, 20922.0, 26341.0, 25070.0, 30380.0, 31745.0, 33283.0, 28152.0, 29515.0, 30804.0, 31533.0, 34126.0, 33755.0, 29861.0, 28917.0, 25306.0, 27051.0, 28680.0, 31242.0, 32114.0, 32491.0, 26612.0, 25517.0, 27539.0, 28486.0, 28819.0, 36188.0, 32796.0, 27631.0, 22412.0, 24385.0, 27327.0]}],
                        {"hovermode": "x unified", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "US Daily Increase in Cases:"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Number of People"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('61d0bb46-ca4a-411b-a6cb-4f0b264ff3b2');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="718b5bc1-8f3e-4551-a891-4d87bed93e59" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("718b5bc1-8f3e-4551-a891-4d87bed93e59")) {
                    Plotly.newPlot(
                        '718b5bc1-8f3e-4551-a891-4d87bed93e59',
                        [{"hovertemplate": " %{y:.0f}", "marker": {"color": "red"}, "name": "Deaths", "type": "bar", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 5.0, 1.0, 4.0, 1.0, 2.0, 3.0, 4.0, 1.0, 6.0, 8.0, 5.0, 8.0, 9.0, 15.0, 26.0, 34.0, 31.0, 94.0, 91.0, 93.0, 144.0, 200.0, 222.0, 308.0, 410.0, 539.0, 466.0, 689.0, 772.0, 1175.0, 1134.0, 1420.0, 1325.0, 1609.0, 1520.0, 1519.0, 2297.0, 2079.0, 1985.0, 2078.0, 2009.0, 1744.0, 1784.0, 2392.0, 2472.0, 2093.0, 2584.0, 2342.0, 1192.0, 1714.0, 2427.0, 2326.0, 2312.0, 1769.0, 2262.0, 1126.0, 1378.0, 2096.0, 2612.0]}],
                        {"hovermode": "x unified", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "US Daily Increase in Deaths:"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Number of People"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('718b5bc1-8f3e-4551-a891-4d87bed93e59');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>



<div>


            <div id="9dc5cfd3-c865-48a8-b4fb-1d314715d9bb" class="plotly-graph-div" style="height:525px; width:100%;"></div>
            <script type="text/javascript">
                require(["plotly"], function(Plotly) {
                    window.PLOTLYENV=window.PLOTLYENV || {};

                if (document.getElementById("9dc5cfd3-c865-48a8-b4fb-1d314715d9bb")) {
                    Plotly.newPlot(
                        '9dc5cfd3-c865-48a8-b4fb-1d314715d9bb',
                        [{"hovertemplate": " %{y:.0f}", "marker": {"color": "green"}, "name": "Recovered", "type": "bar", "x": [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98], "y": [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 3.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 2.0, 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.0, 0.0, 4.0, 0.0, 0.0, 0.0, 5.0, 0.0, 88.0, 16.0, 26.0, 29.0, 2.0, 0.0, 170.0, 13.0, 320.0, 188.0, 203.0, 1593.0, 2979.0, 1380.0, 1450.0, 527.0, 706.0, 4945.0, 2796.0, 2133.0, 2182.0, 1796.0, 1851.0, 3380.0, 2480.0, 1718.0, 10494.0, 4281.0, 4333.0, 2607.0, 3842.0, 6295.0, 5497.0, 1992.0, 2875.0, 2162.0, 2837.0, 18876.0, 1293.0, 6616.0, 4436.0, 4512.0, 4784.0]}],
                        {"hovermode": "x unified", "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "title": {"text": "US Daily Increase in Recoveries"}, "xaxis": {"title": {"text": "Days since 1/22/20"}}, "yaxis": {"title": {"text": "Number of People"}}},
                        {"responsive": true}
                    ).then(function(){

var gd = document.getElementById('9dc5cfd3-c865-48a8-b4fb-1d314715d9bb');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })
                };
                });
            </script>
        </div>

