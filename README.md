# Ransomware Data Visualization and Analytics

Ransomware data visualization used to navigate a database and analyze trends of global ransomware attacks by various properties such as location, sector, year, revenue of company, whether ransom was paid, and more.

![image](https://github.com/user-attachments/assets/d9fdcbde-976c-4e63-bb61-238e83a58aef)

## Getting Started

### Dependencies

* Server Hosting Capability (Python, etc.)

### Installing

* Clone the repository with `git clone https://github.com/williamt1117/RansomwareDataVisualization`

### Executing program

Start the server hosting the cloned repository.

If using Python 3.X.X...
* Navigate to the directory in terminal
* start the server with `python3 -m http.server PORT_NUMBER`
* open a web browser and enter into the address bar `localhost:PORT_NUMBER`

## Description

This project is a ransomware data visualization that aims to analyze trends within a dataset of ransomware attacks from the past decade across the world.
Analyzing these trends is done with the intention of being able to answer questions such as:
* Does the year or month have have correlation with the targeted sector?
* Are there relationships between location, organization size, and likelihood of an attack?
* What are the common characteristics of organizations who chose to pay or not pay the ransom?

The dataset consists of approximately 600 data cases and many data dimensions, although only 8 data dimensions were used as many were duplicates or obsolete.
Data dimensions used were name, sector, revenue, story, year, ransom paid, continent, and country.

This visualization uses a circle packing diagram as the main method of exploring and filtering the data.
The grouping for the circle packing is decided by the user and can be switched between location, sector, ransom paid, and year. Up to 3 levels of grouping can be selected at once.
Each opaque circle represents a ransomware attack, with the color encoding representing whether ransom was paid, refused, or unknown. Size of the circle represents the companies size in revenue.
Hovering over a ransomware attack displays a tooltip with the name of the attack (typically the company name), the revenue of the targeted company, and a short story (if included).

| ![image](https://github.com/user-attachments/assets/2f63e7b3-06e6-4a79-b8bd-a75455c3cbea) |
|:---:|
| *Figure 1: Attached Legend* |

| ![image](https://github.com/user-attachments/assets/268a0d70-2dc5-45bd-aa0f-90dd118c8080) |
|:---:|
| *Figure 2: Displayed Tooltip on Hover* |

Exploring the circle packing diagram can be done by clicking on the corresponding translucent circle grouping you want to visit. Doing so will zoom to that location and filter the data sent to the supporting visualizations to only what is seen within that scope.

![unknown_2024 11 27-00 39-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/f2b28124-363b-4a83-a815-25cc5bb7805b)

The circle packing diagram has 2 supporting visualizations consisting of a histogram and a pie chart.

The histogram can be switched to group by years or by months. The height represents how many data cases were found within that time range.
The pie chart visually shows the ratio of how many ransoms were paid, how many were refused, and how many are unknown. It additionally shows the number of cases and the associated percentage.

### Questions

The project's goal is to answer the following questions:
* Does the year or month have have correlation with the targeted sector?
* Are there relationships between location, organization size, and likelihood of an attack?
* What are the common characteristics of organizations who chose to pay or not pay the ransom?

To determine if the year or month have have correlation with the targeted sector we can group the visualization by sector and change the histogram to display by month.
Visiting the healthcare grouping we see ransomware attacks die down in December. Visiting the government grouping we see ransomware attacks die down in December as well.

All Sectors | Healthcare | Government
:-------------------------:|:-------------------------:|:-------------------------:
![image](https://github.com/user-attachments/assets/1d6fbbd0-bd69-4ece-a614-a0bad02dd390) | ![image](https://github.com/user-attachments/assets/ce1269ad-8f83-4396-8ba3-3f7877c77095) | ![image](https://github.com/user-attachments/assets/f584dfd1-0228-4539-b2c2-8c39b2b17a13)

Additionally, visiting the academic grouping we see ransomware attacks slow down during the late summer and ramp back up as the september semester starts.

All Sectors | Academic
:-------------------------:|:-------------------------:
![image](https://github.com/user-attachments/assets/1d6fbbd0-bd69-4ece-a614-a0bad02dd390) | ![image](https://github.com/user-attachments/assets/a955e280-2e23-4fe0-ba12-d808c90dea5e)

Note: While the data appears to support these claims, since a small subset of the data is being explored, coincidental observations are possible.

Changing our histogram to year grouping and visiting the tech sector we can see that tech attacks have decreased in recent years whereas government and academic sectors have been increasing. This possibly hints to tech organizations having more robust security recently whereas other sectors have more outdated security, hence being targeted more.

All Sectors | Tech | Government | Academic
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
![image](https://github.com/user-attachments/assets/131ac770-1ae4-4bc6-95c2-e3f28a22a753) | ![image](https://github.com/user-attachments/assets/77d6ca69-5b67-4418-b17f-b118f313c954) | ![image](https://github.com/user-attachments/assets/6e1d7804-3ebe-4179-9fe7-d89ffb7e55e3) | ![image](https://github.com/user-attachments/assets/a7e7a82c-4479-4331-93b8-80b37cce97dc)

To determine whether location changes likelihood of a ransomware attack we can group by location and visually see that North America and Europe account for most of the ransomware attacks.
While this could mean that more ransomware attacks happen in these locations, since this is not a complete dataset it is possible that the dataset simply contains more data from these continents.

![image](https://github.com/user-attachments/assets/1d2dc5e1-ebec-4b57-8915-643d4fe9c26c)

Grouping by ransom paid we can see that the size of the company has little to no correlation with whether the ransom is paid.

![image](https://github.com/user-attachments/assets/e62227c0-a4f6-4020-9d70-716c811a1f8e)

To determine whether location has correlation with paying the ransom or refusing it we can group by location and visit Asia, Oceania, Africa and North America and view the pie chart to see that Asia, Oceania, and Africa pay ransoms less frequently and North America pays ransoms the most.

All Continents | Asia | Oceania | Africa | North America
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
![image](https://github.com/user-attachments/assets/b1af5511-56ea-4f9d-863a-f0aac0be9fa6) | ![image](https://github.com/user-attachments/assets/7f4b1056-9f86-41d5-8cd5-4f68bab447a2) | ![image](https://github.com/user-attachments/assets/cc37b677-f041-4812-95be-2a10a0690a39) | ![image](https://github.com/user-attachments/assets/db36ceff-6861-44ce-903e-95a46b6f441c) | ![image](https://github.com/user-attachments/assets/2e4099a8-6ea3-4106-a742-fad787eb343e)

## Authors

William Trottier [(GitHub)](https://github.com/williamt1117) [(LinkedIn)](https://www.linkedin.com/in/william-trottier/)

Jiayue Wong [(GitHub)](https://github.com/cronchyjia) [(LinkedIn)](https://www.linkedin.com/in/jiayue-wong/)
