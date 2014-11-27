devel_queries
=============

Drupal module to log queries happening for each webrequests (ajax included)

# Why this module ? 
     Another module inspired from Devel  !!! 

     Our intention behind this module was to log the queries for a particular request. 
     You might think that *Devel* already does this. Yes, it does, when we enable 
     "Enable Query Log" in Devel Settings Page. 
     
     But unfortunately, it does not log Ajax requests.  :( 
     I don't know why, there might be some valid reasons behind it. 

     Hence, this module.  So, 2 main reasons behind this module. 
     * Devel does not capture ajax requests. 
     * I want the list of all the actual queries, not the drupal query object in json format. 
       Hmm, yes. Drupal logs all the query objects as json in tmp://devel_querylog

# How to use this ? 
    * Download & Enable this module. [drush en devel_queries -y]
    * Thats it, this will log all queries for all requests now. 
    * All queries will be logged in Drupal temporary filesystem 
       - tmp://devel_queries/
  
# Sample log file 

```

    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    Summary
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    Number of queries : 13
    Url :  /js/admin_menu/cache/a274ff1d2b631a2402afa0a384510027


    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    Queries
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    SELECT cid, data, created, expire, serialized FROM cache WHERE cid IN ('theme_registry:runtime:tweamie')
    SELECT DISTINCT registry.name AS name, registry.filename AS filename
    FROM
    registry registry
    SELECT cid, data, created, expire, serialized FROM cache WHERE cid IN ('t_translation_teamie_placeholders')
    SELECT cid, data, created, expire, serialized FROM cache WHERE cid IN ('entity_info:en')
    SELECT base.uid AS uid, base.name AS name, base.pass AS pass, base.mail AS mail, base.theme AS theme, base.signature AS signature, base.signature_format AS              signature_format, base.created AS created, base.access AS access, base.login AS login, base.status AS status, base.timezone AS timezone, base.language AS language,      base.picture AS picture, base.init AS init, base.data AS data, base.uuid AS uuid
    FROM
    users base
    WHERE  (base.uid IN  (1))

```


# ToDos
   - Create a admin page to set whether enable query log or not. 
   - Configure a list of urls that need to covered for logging.

#Authors 
    - Subramanian Swaminathan (smoneyan@gmail.com)
   




     
  
