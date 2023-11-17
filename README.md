# DYTE-Assignment
db.logs.find({
  $or: [
    { "level": "error" },
    { "message": { $regex: /Failed to connect/i } },
    { "resourceId": "server-1234" },
    {
      "timestamp": {
        $gte: ISODate("2023-09-10T00:00:00Z"),
        $lte: ISODate("2023-09-15T23:59:59Z")
      }
    }
  ]
})
