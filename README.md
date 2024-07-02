# SmartVideoSearch

## Business Scenario

You work for a training organization that recently developed an introductory course on machine learning (ML). The course includes over 40 videos covering a broad range of ML topics. Your task is to create an application that allows students to quickly locate and view video content by searching for topics and key phrases. All videos are stored in an Amazon Simple Storage Service (Amazon S3) bucket, and you need to produce a dashboard to meet your supervisor’s requirements.

## Methodology

### Step 1: Downloading Videos
First, download all the videos from AWS S3 to your local system.

### Step 2: Audio Extraction and Chunking
- Convert each video file to audio.
- Create chunks of the audio file for manageable processing.

### Step 3: Speech Recognition
- Iterate through each audio chunk and extract text using a speech recognition library.
- Merge the extracted text from each chunk to create a file representing the subtitle of the video.

### Step 4: Text Processing
- Save the extracted text and the corresponding file name in a DataFrame.
- Clean and normalize the text using Natural Language Processing (NLP) techniques.

### Step 5: Keyword Extraction
- Extract 30 keywords from each text file using KeyBERT (model='all-mpnet-base-v2').

### Step 6: Similarity Calculation
- Use cosine similarity to match user queries with the extracted keywords and return the most relevant videos.

### Step 7: Dashboard Creation
- Develop a simple dashboard where users can input their search queries.
- Calculate similarity scores and return the 5 best-matched videos to the user.

### Sample Dashboard Interaction

#### User Input: "I want video on ML"
```plaintext
I would like to recommend these 5 videos:
1) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod03_Sect03_part3.mp4
2) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod06_Intro.mp4
3) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod04_Sect02_part1.mp4
4) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod03_Sect07_part2.mp4
5) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod05_Sect01_ver2.mp4
```

#### User Input: "I want video on NLP"
```plaintext
I would like to recommend these 5 videos:
1) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod06_Intro.mp4
2) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod03_Sect03_part3.mp4
3) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod06_Sect01.mp4
4) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod03_Sect07_part2.mp4
5) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod03_Sect02_part3.mp4
```

#### User Input: "I want videos on ImageNet"
```plaintext
I would like to recommend these 5 videos:
1) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod05_WrapUp_ver2.mp4
2) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod03_Sect02_part3.mp4
3) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod05_Sect01_ver2.mp4
4) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod06_Sect02.mp4
5) https://nlp-project-transcribevideos.s3.amazonaws.com/videos/Mod05_Intro.mp4
```

#### User Input: "exit"
```plaintext
Exiting the application.
```

## Requirements

### Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/vrajpatel1411/SmartVideoSearch.git
    cd SmartVideoSearch
    ```

### Running the Application

1. **Open the Jupyter notebook:**

    ```bash
    jupyter notebook
    ```

2. **Run the notebook cells to interact with the application.**
