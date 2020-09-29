# afu_abbaustellen_gis

## TODO
- DB mit "Baskets/Datasets"
- Tests

## Datenbank
```
docker run --rm --name edit-db-abbaustellen -p 7432:5432 --hostname primary -e PG_DATABASE=edit -e PG_LOCALE=de_CH.UTF-8 -e PG_PRIMARY_PORT=5432 -e PG_MODE=primary -e PG_USER=admin -e PG_PASSWORD=admin -e PG_PRIMARY_USER=repl -e PG_PRIMARY_PASSWORD=repl -e PG_ROOT_PASSWORD=secret -e PG_WRITE_USER=gretl -e PG_WRITE_PASSWORD=gretl -e PG_READ_USER=ogc_server -e PG_READ_PASSWORD=ogc_server sogis/oereb-db:latest
```


## Befehle

```
java -jar /Users/stefan/apps/ili2pg-4.4.2/ili2pg-4.4.2.jar --dbhost localhost --dbport 7432 --dbdatabase edit --dbusr admin --dbpwd admin --dbschema afu_abbaustellen --defaultSrsCode 2056 --createGeomIdx --createFk --createFkIdx --createUnique --createEnumTabs --beautifyEnumDispName --createMetaInfo --createNumChecks --nameByTopic --strokeArcs --createBasketCol --createDatasetCol --modeldir ".;http://models.geo.admin.ch" --models SO_AFU_Abbaustellen_20200918 --schemaimport
```

Import Geometrie-Daten ("QGIS")
```
java -jar /Users/stefan/apps/ili2pg-4.4.2/ili2pg-4.4.2.jar --dbhost localhost --dbport 7432 --dbdatabase edit --dbusr admin --dbpwd admin --dbschema afu_abbaustellen --defaultSrsCode 2056 --disableValidation --modeldir ".;http://models.geo.admin.ch" --models SO_AFU_Abbaustellen_20200918 --dataset geometrie --import abbaustellen_geometrie.xtf
```

Import Fachdaten ("Uplus")
```
java -jar /Users/stefan/apps/ili2pg-4.4.2/ili2pg-4.4.2.jar --dbhost localhost --dbport 7432 --dbdatabase edit --dbusr admin --dbpwd admin --dbschema afu_abbaustellen --defaultSrsCode 2056 --disableValidation --modeldir ".;http://models.geo.admin.ch" --models SO_AFU_Abbaustellen_20200918 --dataset fachanwendung --replace abbaustellen_fachanwendung.xml


java -jar /Users/stefan/apps/ili2pg-4.4.2/ili2pg-4.4.2.jar --dbhost localhost --dbport 7432 --dbdatabase edit --dbusr admin --dbpwd admin --dbschema afu_abbaustellen --defaultSrsCode 2056 --disableValidation --modeldir ".;http://models.geo.admin.ch" --models SO_AFU_Abbaustellen_20200918 --dataset fachanwendung --replace abbaustellen_fachanwendung_fehler_fehlende_geometrie.xml
```

Tests ohne Baskets etc.
```
java -jar /Users/stefan/apps/ili2pg-4.4.2/ili2pg-4.4.2.jar --dbhost localhost --dbport 54321 --dbdatabase edit --dbusr admin --dbpwd admin --dbschema afu_abbaustellen --defaultSrsCode 2056 --createGeomIdx --createFk --createFkIdx --createUnique --createEnumTabs --beautifyEnumDispName --createMetaInfo --createNumChecks --nameByTopic --strokeArcs  --modeldir ".;http://models.geo.admin.ch" --models SO_AFU_Abbaustellen_20200918 --schemaimport

java -jar /Users/stefan/apps/ili2pg-4.4.2/ili2pg-4.4.2.jar --dbhost localhost --dbport 54321 --dbdatabase edit --dbusr admin --dbpwd admin --dbschema afu_abbaustellen --defaultSrsCode 2056 --createGeomIdx --createFk --createFkIdx --createUnique --createEnumTabs --beautifyEnumDispName --createMetaInfo --createNumChecks --nameByTopic --strokeArcs  --modeldir ".;http://models.geo.admin.ch" --models SO_AFU_Abbaustellen_20200918 --disableValidation --export fubar.xtf

```



```
java -jar /Users/stefan/apps/ilivalidator-1.11.6/ilivalidator-1.11.6.jar --allObjectsAccessible abbaustellen_geometrie.xtf abbaustellen_fachanwendung.xtf
```