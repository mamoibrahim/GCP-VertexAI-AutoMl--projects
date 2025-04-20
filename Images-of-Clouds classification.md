

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
