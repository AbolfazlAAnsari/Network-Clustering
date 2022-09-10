# Network-Clustering

This is a repository for one of my AI course projects

Network Clustering based on Meta-heuristic algorithms (Genetic - Cuckoo optimization)


<html>
<head>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/vis/4.16.1/vis.css" type="text/css" />
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/vis/4.16.1/vis-network.min.js"> </script>
<center>
<h1></h1>
</center>

<!-- <link rel="stylesheet" href="../node_modules/vis/dist/vis.min.css" type="text/css" />
<script type="text/javascript" src="../node_modules/vis/dist/vis.js"> </script>-->

<style type="text/css">

        #mynetwork {
            width: 100%;
            height: 750x;
            background-color: #222222;
            border: 1px solid lightgray;
            position: relative;
            float: left;
        }

        

        

        
</style>

</head>

<body>
<div id = "mynetwork"></div>


<script type="text/javascript">

    // initialize global variables.
    var edges;
    var nodes;
    var network; 
    var container;
    var options, data;

    
    // This method is responsible for drawing the graph, returns the drawn network
    function drawGraph() {
        var container = document.getElementById('mynetwork');
        
        

        // parsing and collecting nodes and edges from the python
        nodes = new vis.DataSet([{"font": {"color": "white"}, "id": 1, "label": 1, "shape": "dot"}, {"font": {"color": "white"}, "id": 2, "label": 2, "shape": "dot"}, {"font": {"color": "white"}, "id": 3, "label": 3, "shape": "dot"}, {"font": {"color": "white"}, "id": 4, "label": 4, "shape": "dot"}, {"font": {"color": "white"}, "id": 5, "label": 5, "shape": "dot"}, {"font": {"color": "white"}, "id": 6, "label": 6, "shape": "dot"}, {"font": {"color": "white"}, "id": 7, "label": 7, "shape": "dot"}, {"font": {"color": "white"}, "id": 8, "label": 8, "shape": "dot"}, {"font": {"color": "white"}, "id": 9, "label": 9, "shape": "dot"}, {"font": {"color": "white"}, "id": 10, "label": 10, "shape": "dot"}, {"font": {"color": "white"}, "id": 11, "label": 11, "shape": "dot"}, {"font": {"color": "white"}, "id": 12, "label": 12, "shape": "dot"}, {"font": {"color": "white"}, "id": 13, "label": 13, "shape": "dot"}, {"font": {"color": "white"}, "id": 14, "label": 14, "shape": "dot"}, {"font": {"color": "white"}, "id": 15, "label": 15, "shape": "dot"}, {"font": {"color": "white"}, "id": 16, "label": 16, "shape": "dot"}, {"font": {"color": "white"}, "id": 17, "label": 17, "shape": "dot"}, {"font": {"color": "white"}, "id": 18, "label": 18, "shape": "dot"}, {"font": {"color": "white"}, "id": 19, "label": 19, "shape": "dot"}, {"font": {"color": "white"}, "id": 20, "label": 20, "shape": "dot"}, {"font": {"color": "white"}, "id": 21, "label": 21, "shape": "dot"}, {"font": {"color": "white"}, "id": 22, "label": 22, "shape": "dot"}, {"font": {"color": "white"}, "id": 23, "label": 23, "shape": "dot"}, {"font": {"color": "white"}, "id": 24, "label": 24, "shape": "dot"}, {"font": {"color": "white"}, "id": 25, "label": 25, "shape": "dot"}, {"font": {"color": "white"}, "id": 26, "label": 26, "shape": "dot"}, {"font": {"color": "white"}, "id": 27, "label": 27, "shape": "dot"}, {"font": {"color": "white"}, "id": 28, "label": 28, "shape": "dot"}, {"font": {"color": "white"}, "id": 29, "label": 29, "shape": "dot"}, {"font": {"color": "white"}, "id": 30, "label": 30, "shape": "dot"}, {"font": {"color": "white"}, "id": 31, "label": 31, "shape": "dot"}, {"font": {"color": "white"}, "id": 32, "label": 32, "shape": "dot"}, {"font": {"color": "white"}, "id": 33, "label": 33, "shape": "dot"}, {"font": {"color": "white"}, "id": 34, "label": 34, "shape": "dot"}, {"color": "white", "font": {"color": "white"}, "id": 101, "label": 101, "shape": "dot"}, {"color": "white", "font": {"color": "white"}, "id": 102, "label": 102, "shape": "dot"}, {"color": "white", "font": {"color": "white"}, "id": 103, "label": 103, "shape": "dot"}, {"color": "white", "font": {"color": "white"}, "id": 104, "label": 104, "shape": "dot"}, {"color": "lime", "font": {"color": "white"}, "id": 105, "label": 105, "shape": "dot"}, {"color": "lime", "font": {"color": "white"}, "id": 106, "label": 106, "shape": "dot"}, {"color": "lime", "font": {"color": "white"}, "id": 107, "label": 107, "shape": "dot"}, {"color": "white", "font": {"color": "white"}, "id": 108, "label": 108, "shape": "dot"}, {"color": "cyan", "font": {"color": "white"}, "id": 109, "label": 109, "shape": "dot"}, {"color": "cyan", "font": {"color": "white"}, "id": 110, "label": 110, "shape": "dot"}, {"color": "lime", "font": {"color": "white"}, "id": 111, "label": 111, "shape": "dot"}, {"color": "white", "font": {"color": "white"}, "id": 112, "label": 112, "shape": "dot"}, {"color": "white", "font": {"color": "white"}, "id": 113, "label": 113, "shape": "dot"}, {"color": "white", "font": {"color": "white"}, "id": 114, "label": 114, "shape": "dot"}, {"color": "cyan", "font": {"color": "white"}, "id": 115, "label": 115, "shape": "dot"}, {"color": "cyan", "font": {"color": "white"}, "id": 116, "label": 116, "shape": "dot"}, {"color": "lime", "font": {"color": "white"}, "id": 117, "label": 117, "shape": "dot"}, {"color": "white", "font": {"color": "white"}, "id": 118, "label": 118, "shape": "dot"}, {"color": "cyan", "font": {"color": "white"}, "id": 119, "label": 119, "shape": "dot"}, {"color": "white", "font": {"color": "white"}, "id": 120, "label": 120, "shape": "dot"}, {"color": "cyan", "font": {"color": "white"}, "id": 121, "label": 121, "shape": "dot"}, {"color": "white", "font": {"color": "white"}, "id": 122, "label": 122, "shape": "dot"}, {"color": "cyan", "font": {"color": "white"}, "id": 123, "label": 123, "shape": "dot"}, {"color": "yellow", "font": {"color": "white"}, "id": 124, "label": 124, "shape": "dot"}, {"color": "yellow", "font": {"color": "white"}, "id": 125, "label": 125, "shape": "dot"}, {"color": "yellow", "font": {"color": "white"}, "id": 126, "label": 126, "shape": "dot"}, {"color": "cyan", "font": {"color": "white"}, "id": 127, "label": 127, "shape": "dot"}, {"color": "yellow", "font": {"color": "white"}, "id": 128, "label": 128, "shape": "dot"}, {"color": "yellow", "font": {"color": "white"}, "id": 129, "label": 129, "shape": "dot"}, {"color": "cyan", "font": {"color": "white"}, "id": 130, "label": 130, "shape": "dot"}, {"color": "cyan", "font": {"color": "white"}, "id": 131, "label": 131, "shape": "dot"}, {"color": "yellow", "font": {"color": "white"}, "id": 132, "label": 132, "shape": "dot"}, {"color": "cyan", "font": {"color": "white"}, "id": 133, "label": 133, "shape": "dot"}, {"color": "cyan", "font": {"color": "white"}, "id": 134, "label": 134, "shape": "dot"}]);
        edges = new vis.DataSet([{"from": 1, "to": 2}, {"from": 1, "to": 3}, {"from": 1, "to": 4}, {"from": 1, "to": 5}, {"from": 1, "to": 6}, {"from": 1, "to": 7}, {"from": 1, "to": 8}, {"from": 1, "to": 9}, {"from": 1, "to": 11}, {"from": 1, "to": 12}, {"from": 1, "to": 13}, {"from": 1, "to": 14}, {"from": 1, "to": 18}, {"from": 1, "to": 20}, {"from": 1, "to": 22}, {"from": 1, "to": 32}, {"from": 2, "to": 3}, {"from": 2, "to": 4}, {"from": 2, "to": 8}, {"from": 2, "to": 14}, {"from": 2, "to": 18}, {"from": 2, "to": 20}, {"from": 2, "to": 22}, {"from": 2, "to": 31}, {"from": 3, "to": 4}, {"from": 3, "to": 8}, {"from": 3, "to": 9}, {"from": 3, "to": 10}, {"from": 3, "to": 14}, {"from": 3, "to": 28}, {"from": 3, "to": 29}, {"from": 3, "to": 33}, {"from": 4, "to": 8}, {"from": 4, "to": 13}, {"from": 4, "to": 14}, {"from": 5, "to": 7}, {"from": 5, "to": 11}, {"from": 6, "to": 7}, {"from": 6, "to": 11}, {"from": 6, "to": 17}, {"from": 7, "to": 17}, {"from": 9, "to": 31}, {"from": 9, "to": 33}, {"from": 9, "to": 34}, {"from": 10, "to": 34}, {"from": 14, "to": 34}, {"from": 15, "to": 33}, {"from": 15, "to": 34}, {"from": 16, "to": 33}, {"from": 16, "to": 34}, {"from": 19, "to": 33}, {"from": 19, "to": 34}, {"from": 20, "to": 34}, {"from": 21, "to": 33}, {"from": 21, "to": 34}, {"from": 23, "to": 33}, {"from": 23, "to": 34}, {"from": 24, "to": 26}, {"from": 24, "to": 28}, {"from": 24, "to": 30}, {"from": 24, "to": 33}, {"from": 24, "to": 34}, {"from": 25, "to": 26}, {"from": 25, "to": 28}, {"from": 25, "to": 32}, {"from": 26, "to": 32}, {"from": 27, "to": 30}, {"from": 27, "to": 34}, {"from": 28, "to": 34}, {"from": 29, "to": 32}, {"from": 29, "to": 34}, {"from": 30, "to": 33}, {"from": 30, "to": 34}, {"from": 31, "to": 33}, {"from": 31, "to": 34}, {"from": 32, "to": 33}, {"from": 32, "to": 34}, {"from": 33, "to": 34}, {"from": 101, "to": 102}, {"from": 101, "to": 103}, {"from": 101, "to": 104}, {"from": 101, "to": 105}, {"from": 101, "to": 106}, {"from": 101, "to": 107}, {"from": 101, "to": 108}, {"from": 101, "to": 109}, {"from": 101, "to": 111}, {"from": 101, "to": 112}, {"from": 101, "to": 113}, {"from": 101, "to": 114}, {"from": 101, "to": 118}, {"from": 101, "to": 120}, {"from": 101, "to": 122}, {"from": 101, "to": 132}, {"from": 102, "to": 103}, {"from": 102, "to": 104}, {"from": 102, "to": 108}, {"from": 102, "to": 114}, {"from": 102, "to": 118}, {"from": 102, "to": 120}, {"from": 102, "to": 122}, {"from": 102, "to": 131}, {"from": 103, "to": 104}, {"from": 103, "to": 108}, {"from": 103, "to": 109}, {"from": 103, "to": 110}, {"from": 103, "to": 114}, {"from": 103, "to": 128}, {"from": 103, "to": 129}, {"from": 103, "to": 133}, {"from": 104, "to": 108}, {"from": 104, "to": 113}, {"from": 104, "to": 114}, {"from": 105, "to": 107}, {"from": 105, "to": 111}, {"from": 106, "to": 107}, {"from": 106, "to": 111}, {"from": 106, "to": 117}, {"from": 107, "to": 117}, {"from": 109, "to": 131}, {"from": 109, "to": 133}, {"from": 109, "to": 134}, {"from": 110, "to": 134}, {"from": 114, "to": 134}, {"from": 115, "to": 133}, {"from": 115, "to": 134}, {"from": 116, "to": 133}, {"from": 116, "to": 134}, {"from": 119, "to": 133}, {"from": 119, "to": 134}, {"from": 120, "to": 134}, {"from": 121, "to": 133}, {"from": 121, "to": 134}, {"from": 123, "to": 133}, {"from": 123, "to": 134}, {"from": 124, "to": 126}, {"from": 124, "to": 128}, {"from": 124, "to": 130}, {"from": 124, "to": 133}, {"from": 124, "to": 134}, {"from": 125, "to": 126}, {"from": 125, "to": 128}, {"from": 125, "to": 132}, {"from": 126, "to": 132}, {"from": 127, "to": 130}, {"from": 127, "to": 134}, {"from": 128, "to": 134}, {"from": 129, "to": 132}, {"from": 129, "to": 134}, {"from": 130, "to": 133}, {"from": 130, "to": 134}, {"from": 131, "to": 133}, {"from": 131, "to": 134}, {"from": 132, "to": 133}, {"from": 132, "to": 134}, {"from": 133, "to": 134}]);

        // adding nodes and edges to the graph
        data = {nodes: nodes, edges: edges};

        var options = {
    "configure": {
        "enabled": false
    },
    "edges": {
        "color": {
            "inherit": true
        },
        "smooth": {
            "enabled": false,
            "type": "continuous"
        }
    },
    "interaction": {
        "dragNodes": true,
        "hideEdgesOnDrag": false,
        "hideNodesOnDrag": false
    },
    "physics": {
        "barnesHut": {
            "avoidOverlap": 0,
            "centralGravity": 0.3,
            "damping": 0.09,
            "gravitationalConstant": -80000,
            "springConstant": 0.001,
            "springLength": 250
        },
        "enabled": true,
        "stabilization": {
            "enabled": true,
            "fit": true,
            "iterations": 1000,
            "onlyDynamicEdges": false,
            "updateInterval": 50
        }
    }
};
        
        

        

        network = new vis.Network(container, data, options);
	 
        


        

        return network;

    }

    drawGraph();

</script>
</body>
</html>
