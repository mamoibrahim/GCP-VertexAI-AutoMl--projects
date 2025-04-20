

# 1- we made a gs bucket and copied the dataset into the bucket we made (the data was in a gcp's public datasets )

1- 


```
gsutil mb -p $GOOGLE_CLOUD_PROJECT \
    -c standard    \
    -l us \
    gs://$GOOGLE_CLOUD_PROJECT-vcm/
```

```
export BUCKET=$GOOGLE_CLOUD_PROJECT-vcm
```

```
gsutil -m cp -r gs://spls/gsp223/images/* gs://${BUCKET}
```
![image](https://github.com/user-attachments/assets/1e84a6e1-c4b0-4292-9560-baff18e573f8)


# 2- Now that your training data is in Cloud Storage, we need a way for AutoML to access it. Typically, we'd create a CSV file where each row contains a URL to a training image and the associated label for that image.

```
gsutil cp gs://spls/gsp223/data.csv .
```

```
sed -i -e "s/placeholder/${BUCKET}/g" ./data.csv
```

```
gsutil cp ./data.csv gs://${BUCKET}
```

![image](https://github.com/user-attachments/assets/ef73a9cd-ce53-4cb8-9657-264e54b28816)


# 3- creating a VertexAi dataset 


![image](https://github.com/user-attachments/assets/e919b5c8-875a-40ba-b215-fc9eca6837b5)

## after this we will choose to import data from Cloud Storage and select the csv file 

# 5- impoting and inspectiong the data 

![image](https://github.com/user-attachments/assets/f17afcd4-aee3-499f-ae6d-93112d796f15)



# 5- training 

![image](https://github.com/user-attachments/assets/687879ed-129e-46b8-9524-1530629da7db)

![image](https://github.com/user-attachments/assets/3926d327-5103-42ad-b365-bb2300b01a1a)




# 6- generating predictions from the endpoint

![image](https://github.com/user-attachments/assets/a3f40f67-5828-4200-993c-80027082b200)

![image](https://github.com/user-attachments/assets/facb85cc-2d6d-442e-bdec-69fa1cb1ff3f)

