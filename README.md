# 🚀 Movie Explorer Development and Deployment Project (Linux Based Kubenetes Deployment) – Discover Your Favorite Films https://681f8a3032fbf14a5c5f3e73--neon-peony-8fec6a.netlify.app/

MTube is a modern and intuitive movie discovery web app that lets users explore the latest trending films, search for favorites, view detailed movie info, and watch trailers — all in one place. Powered by TMDB and YouTube APIs, MTube offers a smooth browsing experience with a user-friendly interface, personalized search, and real-time data fetching.
# Development Stage
# 1] Explaining project setup
✔️ Initialized React App with Vite
Created a fast and optimized React project using Vite for rapid development and hot reloading

✔️ Installed Node Modules
Installed all required project dependencies

✔️ Set Up Global State Management with Redux Toolkit
Installed Redux Toolkit and React-Redux to manage application-wide state (store movie details)

✔️ Styled the App with Tailwind CSS
Integrated Tailwind CSS for utility-first styling

✔️ Initialized Git for Version Control
Initialized a Git repository to track changes and enable collaboration

# 2] API usage
✔️TMDb API: All movie data (Overview,Images, Dates, Ratings and Go to https://developer.themoviedb.org/)

✔️YouTube API: Trailer fetching (Go to https://console.cloud.google.com/apis.)

✔️Axios: Axios is widely used to retrieve data from RESTful APIs, allowing applications to interact with backend services. 

✔️Postman: Manual API testing before integration

# 3] Features Implemented
✔️ Login Screen

The login screen validates user input against default credentials (username: admin, password: admin). Upon correct entry, it smoothly redirects to the Home page, ensuring a seamless and secure entry point into the MTube movie exploration  experience.

![Screenshot (1330)](https://github.com/user-attachments/assets/4bfda42c-0292-4805-a04e-d13acab11d6f)



✔️ Home Screen 

   ✨ Fetching Trending Movies throught TMDB API and show the details
    Trending movies are fetched using Axios from the TMDb REST API and displayed in a responsive grid layout. Each card showcases the poster, title, rating, and release date, adapting seamlessly across mobile and 
    desktop screens for optimal viewing.
    
![Screenshot (1331)](https://github.com/user-attachments/assets/b97374e0-bfb9-4b1c-9a5a-5d12779e0ff3)


   ✨The movie search feature 
    
  uses a search bar integrated with Redux for global state management. When movie details are fetched, they are stored in the Redux store using a detailStore reducer. As the user types 
  in the search bar, results are dynamically filtered from the stored data, ensuring faster response times and reduced redundant API calls.

![Screenshot (1332)](https://github.com/user-attachments/assets/15e09fa1-1941-4b9e-b5fe-aad6a43c2919)


![Screenshot (1343)](https://github.com/user-attachments/assets/0dfa5e4d-3d1a-427a-ae24-be29a5bb6fbf)

  ✨ Fetching Upcoming Movies throught TMDB API and show the details.

![Screenshot (1333)](https://github.com/user-attachments/assets/10751fc8-881c-4de4-b350-a016468e92b6)


  ✨The loading feature uses React’s useEffect and useState to simulate data fetching delays, creating a more realistic experience. A animated is displayed while movies load, enhancing UX 
   with smooth transitions before the actual content appears on screen.

   
![Screenshot (1337)](https://github.com/user-attachments/assets/84f6593e-1ca4-4c4f-97c9-026d57b9187c)


  ✨The movie rating feature uses a React-based star rating system to visually represent the movie’s average vote. Ratings are calculated by converting TMDb's 10-point scale into a 5-star format. Each star is 
    conditionally colored based on the score, enhancing user experience with clear, intuitive feedback for each movie's popularity.
    
  ![Screenshot (1334)](https://github.com/user-attachments/assets/74c952dc-872c-4893-b617-c39ef3418c62)


  ✨Movie trailers are displayed using the YouTube Data API by embedding videos based on trailer keys fetched from TMDb. Axios handles API calls to retrieve relevant trailer links. Users can watch high-quality 
    trailers directly within the app, offering an immersive preview without navigating away from the movie detail page.
    
   ![Screenshot (1336)](https://github.com/user-attachments/assets/e97f449b-d463-4f2c-89a4-5ef444ba4662)

   ✨Global State managment for Redux
   
![Screenshot (1344)](https://github.com/user-attachments/assets/0e190499-d1d8-4847-b3f4-f6789dfeec0c)


# Deployment Stage
# 1] Kubernetes Cluster Setup
For the deployment environment, VirtualBox was used to create three Linux virtual machines. These virtual machines were configured to build a small Kubernetes cluster.

The cluster included:

✔️ One Master Node
The master node was responsible for managing the Kubernetes cluster, scheduling workloads, and controlling cluster operations.

✔️ Two Worker Nodes
The worker nodes were used to run the application pods and handle the actual application workload.

This setup helped to simulate a real-world production-like Kubernetes environment where applications are deployed across multiple nodes instead of running on a single machine like some ancient village server setup.
A Kubernetes cluster was created using kubeadm. After initializing the master node, the worker nodes were joined to the cluster using the kubeadm join command.

The following Kubernetes components were used:

✔️ kube-apiserver
Used to communicate with the Kubernetes cluster.

✔️ kubelet
Runs on each node and manages the pods.

✔️ kube-proxy
Handles networking rules and service communication.

✔️ CoreDNS
Provides DNS resolution inside the Kubernetes cluster.

✔️ Flannel CNI
Flannel was installed as the Container Network Interface to enable pod-to-pod communication across different nodes.

After setting up the cluster, the nodes were verified using:

<img width="1817" height="158" alt="Screenshot 2026-06-10 153826" src="https://github.com/user-attachments/assets/6ed996f9-2cda-4795-bde0-f4a69e86d007" />

# 2] Docker Containerization and Push to Docker Hub using Jenkis
The React application was containerized using Docker. A Dockerfile was created to build the application and run it inside a lightweight container.

The application build process included:

✔️ Installing dependencies
✔️ Building the React application
✔️ Serving the production build using Nginx
✔️ Exposing the application through container port 80
 
 <img width="1920" height="1080" alt="Screenshot (146)" src="https://github.com/user-attachments/assets/424d7cc2-5c56-4f65-950f-2d2ee93d3854" />


