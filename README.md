# mil-2525c-generator

***

## Overview

mil-2525c-generator is a node.js service that generates 2525c symbols using the [milsymbol](http://github.com/spatialillusions/milsymbol) library.
Symbols can either be saved to the disk for local use or returned individually to the browser by using the symbol code.

## How to use

Run the javascript file within the ```bin/``` folder to stand up the node.js service.
The node.js service will run on ```localhost:3000``` by default. 
Once the web service is running symbol generation can be accessed through
the ```/symbol/``` route of your browser. 
```
/symbol/get/{symbolCode} - returns svg or png image of the provided symbol code.
/symbol/create/{symbolCode} - generates desired symbol and saves as an .svg file to the disk.
/symbol/create/all - generates every symbol permutation and saves as .svg files to the disk.
*NOTE* The /all route will create every permutation of symbol taking up over 60gbs of space. 
Make sure you have adequate free space on machine before running.
```
## Example

Run the following commands in the command line to stand up the node.js service.

```
git clone https://github.com/ProminentEdge/mil-2525c-generator.git
npm install
npm start
```
Once the service is running, open your browser and navigate to the following url: [http://localhost:3000/symbol/get/iaaxscc-----](http://localhost:3000/symbol/get/iaaxscc-----)
You should see the generated symbol displayed in your browser. 

Alternatively, if you would like to save the image to an svg file for local use the following url can be used: [http://localhost:3000/symbol/create/iaaxscc-----](http://localhost:3000/symbol/create/iaaxscc-----).  If you would like to generate a png, simply add `.png` to the route: [http://localhost:3000/symbol/create/iaaxscc-----.png](http://localhost:3000/symbol/create/iaaxscc-----.png)
After navigating to this url, the generated symbol should be saved to an svg file located one folder level up from the bin directory by default.
