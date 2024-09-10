# MongoDB
MongoDB - Assessment
1.fetch the result by sorting on "education" column in ascending order
  db.userdetails.aggregate([{$sort:{education:-1}}])
2.fetch the result by sorting on "education" column in descending order
    db.userdetails.aggregate([{$sort:{education:1}}])
3.fetch the result by sorting on "education" column in ascending order and "password" column in descending order
     db.userdetails.aggregate([{$sort:{education:1, password:-1}}])
4.fetch first two documents from the collection "userdetails"
     db.userdetails.find({}).limit(2)
5.fetch two documents after the first two documents from the collection 'userdetails'
     db.userdetails.find({}).limit(4).skip(2)
6.fetch the two documents after the first document from the collection 'userdetails'
     db.userdetails.find({}).limit(2).skip(1)
7.Specify the number of cheeses per cheesetype. Put the cheesetype in capital letters.
    db.cheeses.aggregate([{$group: {_id: "$properties.cheesetype",count:{$count:{}}}} ] )
8.Give per share the average closing price, the minimum closing price, the maximum closing price and the average number of shares traded per day.
   db.bel20.aggregate([{$group:{_id:"$name",maximum: {$max:"$price.end"}}}])
   db.bel20.aggregate([{$group:{_id:"$name",minimum: {$min:"$price.end"}}}])
   db.bel20.aggregate([{$group:{_id:"$name",average: {$avg:"$price.end"}}}])
