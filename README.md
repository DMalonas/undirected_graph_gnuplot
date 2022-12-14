
# undirected_graph_gnuplot
Create an undirected graph, check if it is connected (not more than one components), calculate the adjacency matrix and lists, and then use the available data to plot it using gnuplot.


Link to Github r with all the explanation videos (uploading them all here, makes downloading the project slow): https://github.com/DMalonas/undirected_graph_gnuplot_videos




First create a graph by requesting the number of nodes and then edges. This process creates the corresponding adjacency matrix.
If its not comprised by a single component, which the method isConnected evaluates via the use of the bfs algorithm, then
request from the user to provide details for a new graph again.
##
If the graph is correct, calculate the adjacency lists, using the struct Graph data structure, and return the graph::struct Graph variable,
so the method responsible for printing the adjacency lists can use it to display them on the terminal.
##
Then, process the adjacency matrix to extract nodes info into vertices.dat, and edges info into edges.dat data files.
These file will later be used by the plotGraph method to put together a final graph.dat file which contains the necessary 
ininformation and in the appropriate format, for the gnuplot script to read and draw the graph.
##
Then, enter the main user menu, and ask the user to choose if they want to insert, or delete a node or search for one. Or if they
want to plot the graph. If they choose to insert a new node, the adjacency matrix and lists as well as the vertices.dat and edges.dat
are updated. The same is true for the delete node choice. When checking if a node exists, again, we simply check the adjacency matrix.
When the user picks the plot-graph choice, the plotGraph method is called. There, all the information from vertices.dat and edges.dat
is extracted and fed into graph.dat. 
*For vertices, we call a layout method that gets a list of vertices and after generating a random float x, y
*pair of values, it  uses the pythagorean theorem to check if the hypotenuse distance between the point we are currently processing and all the other points
*is less than the minimum allowed distance. If it is, we try X more times to get it right, and if we dont, then we use the last x,y pair of values that were
*randomly assigned. Now we have node labels, and coordinates for each node, and then we also generate a random rgb color - which ultimately does not seem to
*take effect as the colors are set manually within the gnuplot script. 
*We also generate a random color for each edge, and then we write all the node and edge data into graph.dat.
*Then we use a system command to execute the gnuplot script (called gnuplot_script.gp) that reads from graph.dat to plot the graph.
