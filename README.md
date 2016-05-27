# Budget Data Mining
> Description
  Mines Budget data from uganda's budget PDF documents by first turning them
  to text using poppler's pdftotext utility.

> Since the mining is per vote or section, you can write a bash script to run multiple
  data mining scripts one after the other see [bash script](https://github.com/epicallan/uganda-budget-data/blob/master/samples/bash)

> All the tables with data as listed in the [config file](https://github.com/epicallan/uganda-budget-data/blob/master/src/config.js)
  have the same table structure save for the overview vote Expenditure table.
  For that particular table pass an overview option
  with in the budget command so as to mine it Eg.
  ```
  budget --overview -f 437 -l 438 -n health-over-views-expenditure 2014-15.pdf
  ```
> A global install of the module will expose the budget command which can be used for
  the data mining.
  ```
    $ budget --help
  ```
  ```
   -h, --help         output usage information
   -V, --version      output the version number
   -f, --first <n>    Add first page
   -l, --last <n>     Add last page
   -o, --overview     indicates we are mining from overview vote expenditure table
   -n, --name [name]  Add resulting csv file name
  ```

  Pass in file location as last argument

  ```
    $ budget -f 100 -l 200 -n health-data allan/samples/2014-15.pdf
  ```

## External requirements

Ensure you have poppler's pdftotext utility installed on your OS's file path
>for linux

```
  sudo apt-get install poppler-utils
```

>for macs

```
  brew cask install pdftotext
```  

## Installation for development
```
$ npm install
```
## Run in development
symlinks the module's script to your systems path making it globally available (See the bin key in package.json)

```
$ npm run link
```

```
npm run dev
```
in another terminal run
```
$ budget -f 444 -l 447 -n health 2014-15.pdf
```

## Run in Production
Adds the module's main script to your systems path(See the bin key in package.json)
```
$  npm install -g
```

```
$  npm run build
```

run the budget data mining command
```
$ budget -f 444 -l 447 -n health 2014-15.pdf
  ```
## License
MIT © [Allan](http://github.com/epicallan)
