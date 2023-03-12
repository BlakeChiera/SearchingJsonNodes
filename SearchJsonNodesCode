import json
import sys
import os

################################################################################

#Temporary Class to put raw data from json to python object
class ObjStruct():
    def __init__(self, **entry):
        self.__dict__.update(entry)


#Class to make the json nodes usuable node objects
class BasicNode(object):

    def __init__(self, Node_id, x_cord, y_cord, connected_nodes):
        self.Node_id = Node_id
        self.x_cord = x_cord
        self.y_cord = y_cord
        self.connected_nodes = connected_nodes
        self.end_node = False
        self.distance_from_start = sys.maxsize

    def update_end_node(self, update_end_node):
        self.end_node = update_end_node


#Class to put the parsed data that can be used in the algorithm
class DANode(object):

    def __init__(self, Node_id):
        self.Node_id = Node_id
        self.connected_nodes = []
        self.distance_from_start = sys.maxint

    def add_connected(self, connected, weight):
        self.connected_nodes[connected] = weight

################################################################################


if __name__ == "__main__":

    #setup of some variables
    nodesArray = []

    os.system('CLS')
    print("###########################################\n")
    filename = input("Name of the json file with objects you would like converted: ")
    try:

        #Receiving the data
        with open(filename, "r") as file:
            #Loading data from json file
            raw_data = json.load(file)

            #turning the json object into a usable python dictionary
            NodesObject = ObjStruct(**raw_data)

            total_BasicNodes_var = len(NodesObject.Nodes)

            #putting the nodes into the unvisited array
            for i in range(total_BasicNodes_var):
                temperary_dict = ObjStruct(**NodesObject.Nodes[i])
                temp_node = BasicNode(temperary_dict.Node_id, temperary_dict.x_cord, temperary_dict.y_cord, temperary_dict.connected_nodes)
                nodesArray.append(temp_node)

    except FileNotFoundError:
        print("File not found, try again. Reminder the name is caps sensitive.")

################################################################################

    os.system('CLS')
    print("###########################################\n")
    print("Now you can search for any info about any of the nodes in this list.")
    #Nodes databased
    DNodes_ids = []
    #String to print the nodes
    PNodes_ids = ""
    for i in range(len(nodesArray)):
        DNodes_ids.append(nodesArray[i].Node_id)
        PNodes_ids += str(nodesArray[i].Node_id) + " | "
    print("- The IDs of the Nodes in the file are: " + PNodes_ids)
    print("- You can then find out the different properties of each using any of the commands below")

    print("- The commands that can be used are, coordinates (x,y), and connected (nodes). After typing these commands\n- you will be prompted with which node to search\n- REMEMBER THESE COMMANDS ARE CASE SENSITIVE!!!\n")
    print("###########################################\n")

    x = input("")
    x = x.split(" ")
    while x[0] != "exit program":
        if x[1] == "coordinates":
            l = DNodes_ids.index(int(x[0]))
            print(str(nodesArray[l].x_cord) + ", " + str(nodesArray[l].y_cord))

        elif x[1] == "connected":
            l = DNodes_ids.index(int(x[0]))
            print(str(nodesArray[l].connected_nodes))

        else:
            print("That command was not recognised, if you do not rememeber the commands they are above.")

        x = input()
        x = x.split(" ")


################################################################################
