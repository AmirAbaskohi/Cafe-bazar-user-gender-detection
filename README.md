# Cafe bazar user gender detection

This is a gender detection model base on applications each user used. The data used for models is for Cafe Bazar and Iranian android app store.

## Data
There is a `parquet` file which is related to data.

#### What is a `parquet` file?
Parquet is an open source file format available to any project in the Hadoop ecosystem. Apache Parquet is designed for efficient as well as performant flat columnar storage format of data compared to row based files like CSV or TSV files.

Parquet uses the record shredding and assembly algorithm which is superior to simple flattening of nested namespaces. Parquet is optimized to work with complex data in bulk and features different ways for efficient data compression and encoding types.  This approach is best especially for those queries that need to read certain columns from a large table. Parquet can only read the needed columns therefore greatly minimizing the IO.

#### Difference between `parquet` and `CSV`
CSV is a simple and widely spread format that is used by many tools such as Excel, Google Sheets, and numerous others can generate CSV files. Even though the CSV files are the default format for data processing pipelines it has some disadvantages:

* Amazon Athena and Spectrum will charge based on the amount of data scanned per query.
* Google and Amazon will charge you according to the amount of data stored on GS/S3.
* Google Dataproc charges are time-based.

Parquet has helped its users reduce storage requirements by at least one-third on large datasets, in addition, it greatly improved scan and deserialization time, hence the overall costs.

![image](https://user-images.githubusercontent.com/50926437/126944456-d7d99b99-9120-4eee-8c10-db7861e1523b.png)


#### Data columns
There are different features in the dataset. `gender` is what we are looking for, but we have also `games`, `apps`, `queries`, and `birth_year`. `games`, `apps`, and `queries` are ids.

The problem here is that these 3 columns are list values.

I turned them into individual columns.

## Models
Different models trained for classifications such as:
* Logistic regression
* KNN
* Random Forest
* Decision Tree
* Dense neural network

here the parameter which was important was `balanced_accuracy` which NN reaced near 74 for this value. Also here is other results:
```
Accuracy:  0.8110490378646803
Balanced Accuracy:  0.7446944528323681
Precision:  0.8657574761748275
Recall:  0.8819886173418146
F1:  0.8737976782752902
```

*Made by Amirhossein Abaskohi*

