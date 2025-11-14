import streamlit as st

#Graph Image
st.image("LabReport_BSD2513_#1.jpg", 
         caption="DFS Graph", 
         use_container_width=True)

#Defination for Graph
graph = {
    'A': ['B', 'D'],
    'B': ['C', 'E', 'G'],
    'C': ['A'],
    'D': ['C'],
    'E': ['H'],
    'F': [],
    'G': ['F'],
    'H': ['F', 'G']
}

#DFS algorithm 
def dfs(graph, node, visited=None, order=None):
    if visited is None:
        visited = set()
    if order is None:
        order = []

    if node not in visited:
        visited.add(node)
        order.append(node)

        for neighbour in graph[node]:
            dfs(graph, neighbour, visited, order)

    return order

#Streamlit UI 
st.title("Depth-First Search (DFS) Traversal")

start = st.text_input("Enter Start Node:", "A").strip().upper()

if st.button("Run DFS"):
    if start in graph:
        traversal = dfs(graph, start)
        st.success("DFS Traversal Order:")
        st.write(" → ".join(traversal))
    else:
        st.error("Invalid start node. Enter A–H only.")

st.caption("Lab Report BSD2513 | DFS Implementation")