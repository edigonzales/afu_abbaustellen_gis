# afu_abbaustellen_gis

```
java -jar /Users/stefan/apps/ili2pg-4.4.2/ili2pg-4.4.2.jar --dbhost localhost --dbport 54321 --dbdatabase edit --dbusr admin --dbpwd admin --dbschema afu_abbaustellen --defaultSrsCode 2056 --createGeomIdx --createFk --createFkIdx --createUnique --createEnumTabs --beautifyEnumDispName --createMetaInfo --createNumChecks --nameByTopic --strokeArcs --createBasketCol --createDatasetCol --modeldir ".;http://models.geo.admin.ch" --models SO_AFU_Abbaustellen_20200918 --schemaimport
```

Tests ohne Baskets etc.
```
java -jar /Users/stefan/apps/ili2pg-4.4.2/ili2pg-4.4.2.jar --dbhost localhost --dbport 54321 --dbdatabase edit --dbusr admin --dbpwd admin --dbschema afu_abbaustellen --defaultSrsCode 2056 --createGeomIdx --createFk --createFkIdx --createUnique --createEnumTabs --beautifyEnumDispName --createMetaInfo --createNumChecks --nameByTopic --strokeArcs  --modeldir ".;http://models.geo.admin.ch" --models SO_AFU_Abbaustellen_20200918 --schemaimport

java -jar /Users/stefan/apps/ili2pg-4.4.2/ili2pg-4.4.2.jar --dbhost localhost --dbport 54321 --dbdatabase edit --dbusr admin --dbpwd admin --dbschema afu_abbaustellen --defaultSrsCode 2056 --createGeomIdx --createFk --createFkIdx --createUnique --createEnumTabs --beautifyEnumDispName --createMetaInfo --createNumChecks --nameByTopic --strokeArcs  --modeldir ".;http://models.geo.admin.ch" --models SO_AFU_Abbaustellen_20200918 --disableValidation --export fubar.xtf

```



```
java -jar /Users/stefan/apps/ilivalidator-1.11.6/ilivalidator-1.11.6.jar --allObjectsAccessible abbaustellen_geometrie.xtf abbaustellen_fachanwendung.xtf
```