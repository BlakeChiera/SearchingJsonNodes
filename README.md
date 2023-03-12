# SearchingJsonNodes
This code is to be used to search through json files that contain nodes and to
find specific data on them.

it has commands to search the properties of the nodes. There is an example of the
json file below.


{
  "Nodes": [
    {
      "Node_id": 0,
      "x_cord":0,
      "y_cord":0,
      "connected_nodes": [2,3]
    },
    {
      "Node_id": 1,
      "x_cord":200,
      "y_cord":50,
      "connected_nodes": [0,3,4]
    },
    {
      "Node_id": 2,
      "x_cord":400,
      "y_cord": 0,
      "connected_nodes": [0,2,1]
    },
    {
      "Node_id": 3,
      "x_cord":670,
      "y_cord":58,
      "connected_nodes": [0,3]
    },
    {
      "Node_id": 4,
      "x_cord":3400,
      "y_cord":80,
      "connected_nodes": [1,2]
    }
  ]
}
