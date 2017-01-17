### Detect faces with Watson Visual Recognition
<p align="center">
  <img src="img/wvr1.png"/ width=300px>
</p>
This SPSS Modeler Node allows you to gather information about people on input photos. Watson Visual Recognition will try to detect where are any faces on photo, age and gender of person whose face it is, and sometime his/her identity.

### Before you start
_To run this SPSS Node, you need a Visual Recognition api key. To get one, you can follow steps below:_

1. **[Sign up](https://console.ng.bluemix.net/registration/?target=%2Fdashboard%2Fapps)** or log in to existing **[IBM Bluemix](https://console.ng.bluemix.net/)** acount.
	
2. In bluemix, go to **Catalog** -> **Watson** -> **[Visual Recognition](https://console.eu-gb.bluemix.net/catalog/services/visual-recognition/?taxonomyNavigation=apps)**, select pricing plan and hit "**create**"
	
3. Go to your **Services** -> **Visual Recognition** -> **Service Credentials**, click on "**View credentials**" and look for "**api_key**".

### Requirements 

* SPSS Modeler v18.0
* SPSS Modeler "**[R Essentials](https://github.com/IBMPredictiveAnalytics/R_Essentials_Modeler/releases)**" plugin
* R with package "**httr**"

### Example stream

WatsonDetectFaces node requires a connected source node. In this example, we are using "Excel" source node with one column - "photoURL".
<p align="center">
  <img src="img/ExampleStream.png"/ width=650px>
</p>

Images used in this example (from wikimedia.org)
<p align="center">
  <img src="img/Amrita_Pritam_(1919_–_2005)_,_in_1948.jpg"/ width=180px>
  <img src="img/BarackObamaportrait.png"/ width=220px>
  <img src="img/George_Bush_signs_the_Federal_Funding_Accountability_and_Transparency_Act_of_2006.jpg"/ width=360px>
</p>

In the node window you must provide the **api key** that you received earlier and a **name of column** in which SPSS Modeler can find photo URLs.
You can also change **Api version** if needed (for more information, you can read Visual Recognition's [API Reference](https://www.ibm.com/watson/developercloud/visual-recognition/api/v3/#detect_faces)).

<p align="center">
  <img src="img/Input.png"/ width=800px>
</p>

### Output

The generated output contains:
* source URL of photo
* information about age with score (score's value is between 0 and 1)
* face size (height and width of rectangle containing photo)
* face position (top-left pixel position of rectangle containing photo)
* gendender and it's score (score's value is between 0 and 1)
* identity name with score - Watson Visual Recognition may recognize person from photo
* identity type is information where recognized person belongs (in example /people/politicians/**IDENTITY**)

<p align="center">
  <img src="img/Output.png"/ width=800px>
</p>
