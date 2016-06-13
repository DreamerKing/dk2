title: MonoDB CRUD 操作
date: 2016-01-16 15:20:32
categories: 
    - MongoDB
tags:
    -MongoDB
---
# 创建文档并插入文档    

插入文档使用 `insert(document)`函数，如果要批量插入，可以使用`batchInser(Array)`函数。   
单个插入
```sh
post = {
     "title" : "MonogoDB的基本操作",
     "content" ："这里详细介绍了一些基本操作。"
     "date" : new Date()
     }
    db.blog.inser(post)
```

插入成功后会返回:`WriteResult({ "nInserted" : 1 })` 其中nInserted表示当前操作插入文档的数量。
以文档数组形式批量插入  
```sh
   db.test.insert([ 
   { "name":"李平", "age":26},
   { "name":"吴晓菲", "age":18}
   ]) 
```  
插入成功后返回：  
```sh
BulkWriteResult({
    "writeErrors" : [ ],
    "writeConcernErrors" : [ ],
    "nInserted" : 2,
    "nUpserted" : 0,
    "nMatched" : 0,
    "nModified" : 0,
    "nRemoved" : 0,
    "upserted" : [ ]
})
``` 

#  更新文档    

更新文档使用`update()`方法。要更新文档中某个字段的值，可以使用如`$set`这类的修改器。
```sh
    db.test.update(
        {"name":"李平"},
        {
          $set:{age:20},
          $currentDate:{lastModified:true}
        )
```

更新成功返回:  
```sh
    WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
```
