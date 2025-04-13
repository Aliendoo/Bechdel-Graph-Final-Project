# Bechdel-Graph-Final-Project

## Overview
This project investigates movie casting data using graph data structures to analyze relationships between actors and movies. The implementation creates a bipartite, undirected graph with vertices representing movies and actors, and edges representing the relationships between them. The project offers various analysis methods including actor-movie relationships, degrees of separation between actors, and a customizable Bechdel Test alternative that examines female representation in movie casts.

## Features
- **Bipartite Graph Implementation**: Custom implementation of an undirected graph where vertices represent either movies or actors
- **Movie-Actor Relationship Analysis**: Methods to find all actors in a movie or all movies an actor has appeared in
- **Degrees of Separation**: Calculate how many "degrees" separate two actors in the Hollywood network
- **Custom Bechdel Test**: User-definable percentage threshold to evaluate female representation in movie casts
- **Graph Visualization**: Save graph data in TGF format for visualization in tools like yEd

## Requirements
- Java Development Kit (JDK)
- javafoundations package (for data structures like ArrayQueue)
- yEd Graph Editor (for visualizing TGF files)

## Installation
1. Clone this repository or download the source files
2. Ensure you have the javafoundations package in your classpath
3. Compile the Java files:
   ```
   javac HollywoodGraph.java
   ```

## Usage

### Creating a Hollywood Graph
```java
// Create a graph from a CSV file containing movie and actor data
HollywoodGraph graph = new HollywoodGraph("data/castGender.txt");
```

### Finding Actor-Movie Relationships
```java
// Get all movies an actor has appeared in
LinkedList movies = graph.findMovies("Jennifer Lawrence");

// Get all actors in a specific movie
LinkedList actors = graph.findActors("The Jungle Book");
```

### Finding Degrees of Separation
```java
// Calculate degrees of separation between two actors
int separation = graph.findSeparation("Megan Fox", "Tyler Perry");
```

### Running the Custom Bechdel Test
```java
// Get list of movies that pass the custom Bechdel test
// (User will be prompted to enter a percentage threshold)
LinkedList passedMovies = graph.findNewBechdelValue();
```

### Saving Graph as TGF for Visualization
```java
// Save the graph in TGF format for visualization
graph.saveTGF("HollywoodGraph.tgf");
```

## File Format
The application expects CSV files with the following format:
- Movie name
- Actor name
- Additional fields (skipped in processing)
- Gender information

Example:
```
"The Jungle Book","Idris Elba","Shere Khan","Supporting","Male"
```

## Implementation Details
- **Graph Structure**: Uses ArrayList for vertices and ArrayList of LinkedLists for adjacency lists
- **Gender Tracking**: Uses Hashtables to track female actors and total actors per movie
- **Separation Algorithm**: Employs Breadth-First Search (BFS) to find the shortest path between actors
- **Bechdel Alternative**: Calculates female representation percentage and compares against user-defined threshold

## Authors
- Aileen Du
- Gwen-Zoe Yang
- Audrey Wang
- Suzanne Xu

## Acknowledgments
- Wellesley College
- CS 230: Data Structures
- Professor Smaranda Sandu
