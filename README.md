# Mini TikTok
This is a **`mini clone`** of the popular video-sharing app **`TikTok`**. It allows users to **create** and **upload** `short videos` with `tags` related to their interests. Other users can **view** and interact with the `videos` by `liking` and `commenting` on them. `Notifications` are sent to users when someone likes or comments on their videos.

## Business Requirements
- The system **`supports multiple users`**
- Users can **`log in to the system`**
- Each user can **`specify a list of interests`** they have, e.g. boxing, cars
- Each user can **`upload a short video with a tag`**
- Each user can **`see videos that have tags related to their interests`**
- Other users can **`like and comment on videos`**
- Users **`receive notifications when someone likes their video or comments`** on it

## Technical Requirements
- Have **`at least 3 microservices`** that encapsulate different business domains
- Use **`synchronous communication (HTTP)`** between **`at least two services`**
- Follow the **`REST conventions`** when designing your APIs
- Use **`asynchronous communication (Kafka)`** between **`at least two services`**
- Use **``caching``** where you think it will make sense
- Use a **`relational database`** of your choice where you think is appropriate
- Use a **`non-relational database (Apache Cassandra)`** for **`only one table`**
- Use **`Docker`** to **`containerize the microservices`**
- Use **`Kubernetes`** to **`orchestrate the containers`**
- **`Deploy your application`**
- Use **`GitHub, branches, pull requests`**

## Implementation Details
### Microservices


#### User service
- Responsible for handling user authentication and authorization. It will communicate with the other services to retrieve user-specific data.

#### Video service
- Responsible for handling video uploads, tags, and fetching videos based on tags.

#### Notification service 
- Responsible for sending notifications to users when their videos are liked or commented on.

#### Communication
- HTTP communication will be used between the user service and video service. The user service will send requests to the video service to fetch videos based on user interests.

- Kafka will be used for asynchronous communication between the video service and the notification service. The video service will send an event to the notification service when a video is liked or commented on.

#### Caching
- We will use Redis for caching video tags to improve the performance of the video service.

####  Databases
- Postgres will be used as the relational database to store user authentication data and other metadata.

- Cassandra will be used as the non-relational database to store video data.

#### Containers
- All microservices will be containerized using Docker for easy deployment and portability.

#### Orchestration
- Kubernetes will be used to orchestrate the containers and manage the deployment of the microservices.
