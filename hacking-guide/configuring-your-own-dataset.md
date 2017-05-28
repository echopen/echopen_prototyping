# local data set \(this is related to version 2.0.\)

For local usage, the data can be found from the `assets/data/raw_data` folder. By default, the local dataset that is used is `data_phantom.csv`.

## Setting your dataset

### Formating the dataset

Suppose you want to use your own dataset. Then

* each line corresponds to an acquisition line
* each row corresponds to sampled data for one acquisition line
* edit the `public void fetchData(BitmapDisplayerFactory bitmapDisplayerFactory)` method in the `MainActivity` and adapt the code this way

### Update the code

```
...
AssetManager assetManager = getResources().getAssets();
InputStream inputStream = assetManager.open("data/raw_data/foo.csv");
...
```

If you do not want to use `OpenCV` but the custom home made scan conversion tool, which we do not encourage to, then you have to set up constants accordingly to the section `Home-made scan conversion` of the `Back End/constants` of this book.

## Putting you data in the echOpen format

In order for the data to be processed, we invite the contributor to follow our [format](http://echopen.org/index.php/Challenge:_Data_format). We are currently migrating our datasets to this format.

