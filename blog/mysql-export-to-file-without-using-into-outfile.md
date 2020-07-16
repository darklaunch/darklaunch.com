Export MySQL without using INTO OUTFILE. App Engine doesn't allow using INTO OUTFILE, so this will work once you are able to connect remotely.
```sh
mysql -u root --database=mydatabase < query.sql | tee exported_data.sql
```