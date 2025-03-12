key IN ("INIT-1", "INIT-2", "INIT-3", "INIT-4") 
OR "Parent Link" IN ("INIT-1", "INIT-2", "INIT-3", "INIT-4") 
OR "Epic Link" IN (SELECT key FROM issue WHERE "Parent Link" IN ("INIT-1", "INIT-2", "INIT-3", "INIT-4"))
ORDER BY "Parent Link", "Epic Link", key ASC
