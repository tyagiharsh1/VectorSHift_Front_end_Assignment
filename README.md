# VectorShift Frontend and Backend Project

## Project Description
This project is a pipeline builder application consisting of a React-based frontend and a FastAPI backend. The frontend provides a drag-and-drop interface for creating and connecting nodes to build data processing pipelines visually. The backend analyzes the submitted pipeline structure to determine properties such as whether the pipeline graph is a Directed Acyclic Graph (DAG).

## Technologies Used
- Frontend: React, ReactFlow, Zustand for state management
- Backend: FastAPI, Python
- Communication: REST API between frontend and backend

## Frontend
The frontend offers a user-friendly drag-and-drop UI built with React and ReactFlow. Users can add different types of nodes (input, LLM, output, text) to the canvas, connect them to form pipelines, and submit the pipeline for analysis. The UI supports snapping to grid, smooth connection lines, and includes controls like zoom and minimap.

## Backend
The backend is a FastAPI application that exposes endpoints to:
- Respond to health check requests
- Parse the submitted pipeline JSON (nodes and edges), build a graph representation, and detect if the graph is a DAG using depth-first search cycle detection.

CORS is enabled to allow requests from the frontend running on localhost:3000.

## Getting Started

### Prerequisites
- Node.js and npm installed (for frontend)
- Python 3.7+ installed (for backend)

### Running the Frontend
1. Navigate to the `frontend` directory:
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the development server:
   ```bash
   npm start
   ```
4. Open [http://localhost:3000](http://localhost:3000) in your browser to use the app.

### Running the Backend
1. Navigate to the `backend` directory:
   ```bash
   cd backend
   ```
2. Install dependencies (preferably in a virtual environment):
   ```bash
   pip install fastapi uvicorn
   ```
3. Start the backend server:
   ```bash
   uvicorn main:app --reload --host 0.0.0.0 --port 8000
   ```

## Usage
- Use the frontend UI to drag and drop nodes onto the canvas.
- Connect nodes to form a pipeline.
- Click the "Submit" button to send the pipeline data to the backend.
- The backend will analyze the pipeline and return information including the number of nodes, number of edges, and whether the pipeline is a DAG.
- Results are displayed in an alert dialog.

## License
This project is provided as-is without any specific license.
