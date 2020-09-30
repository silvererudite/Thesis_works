## Abstract

Mental disorders are an unfortunate reality among the general population nowadays. Conditions like anxiety, depression may seem trivial on the surface but have serious consequences on an individual's life. These disorders have shown to be detrimental to health and hamper a person's general well being. In severe cases, if mental disorders go unnoticed and untreated they can cause permanent damage to one's personality, drive him/her to social isolation and in worst cases compel the person to commit suicide as a means to end their suffering. Therefore, a need for proper detection and awareness of such diseases in a person emerges. Mental disorders may not show physical symptoms in a person but it is possible to find patterns in people with a potential mental disorder and detect them with the help of modern Machine learning techniques. In addition to this, such methods are completely automated and non-invasive; as a result these systems can also help continuously monitor a person's mental state. We propose a fully data driven retrieval based system which learns from the user's conversing pattern trained by a knowledge base of conversations of people suffering from mental disorders and can interact with the user in a conversation-like interface as a companion. Moreover, the system can take various physiological signal readings from the human body as a way to reinforce its prediction.

## Problem statement

In recent years, the world has seen a surge of cases involving mental disorders. Different varieties of such diseases such as depression, anxiety, PTSD are continuously on the rise. Moreover according to [1], such diseases have affected populations of varying age from adolescents to people of old age. Past research has focused mostly on identifying, diagnosing and discussing preventive measures to curb these disorders. In addition to these, other problems for example: proper treatment of mental disorders such as social stigma and discrimination are a hindrance to the patients receiving proper treatment. However, little work has been done to put corrective measures and help people already suffering such disorders with proper care and assistance in our modern world where we have little time to look after ourselves. If these problems persist and all we do is apply traditional treatment methods of going to a psychiatrist and counsellors, which may be possible for some of the affected population, but for the vast majority having access to such treatment facilities is a luxury. Finally, according to [2], extensive studies on population of renowned Western countries have shown that if people with mental disorders remain unaware of their condition or are left untreated, their conditions take turn for the worst as time goes and may lead them to cause personal harm and in extreme cases even commit suicide. Therefore, we intend to solve this problem by using modern technology and ideas that would help detect and monitor people’s mental state. This system would :

- learn from the behavioural patterns in the conversation data 
- learn from some physiological signals readings
- apply analysis and detection techniques

And tie up the findings to identify if users are suffering from aforementioned conditions. In the long run, we envision that such a system would help prevent mental disorders as people would be aware of the gradual changes in their mental state and take preventive measures to curb onset of disease.

## Research Objective**

Our main objective of this research is to design a system that can assess the user's mental health conditions. Our research aims to improve mental health conditions of users especially who might not have access to professional help or are afraid of the social stigma behind mental illness. In addition, it would serve as a companion to the user in his/her time of need. For example, if our user is having anxiety or is depressed our system with the help of EDA(Electro Dermal Activity), PPG (Photoplethysmogram) and EMG (electromyography) sensors predict his condition and try to have an audio conversation to improve user’s mental condition. So first, we have to detect the user's mental health conditions using EDA, PPG and EMG sensors. Then, with the help of our conversable model, the system will try to speak with the user. Here, the model will include a speech to text system that will convert the user's speech to text, a language model to try to understand the user's statements, a seq2seq model that will carry out the conversation and a text to speech system that will turn the system's outputs from text output to audio output. To sum up our research goals are-

1. Creating a system that can
a. predict the user’s mental health condition
b. improve the user’s mental condition through continuous conversation like a human
2. Making the system user friendly
3. Making the system available to the people

*Need for a robust method for providing information about humans emotional state

## Signal Data Analysis 

We have collected 3 sensor datasets namely of EDA, PPG and EMG signals which are relevant to our scope of work. These were previously used in various studies involving human emotions and are widely accepted. EDA signals dataset is extracted from the multimodal WESAD dataset [1], PPG dataset....EMG dataset....

We have planned to process our dataset in two phases. For the first phase, we want to pre-process and analyse the datasets individually. Then for phase two we would combine them and integrate with the chatbot, so that it can serve as a quantitative measure of the user's emotions instead of solely relying on ML algorithms to assess mood. Moreover using these signals gives us a way to confirm our detection/prediction from the ML models we used **. . Analysing these signals is an individual field of study on its own and our goal is to only find a way to translate the seemingly cryptic numbers of the signal readings to meaningful detection of a user's emotional state. Therefore for our purposes our objective is to not reinvent the wheels of signal analysis and find the optimal method to process these signals, but find an acceptable way to make sense of these signals. Thorough background study was done for each of these datasets which involved doing extensive literature reviews and finding appropriate resources to help us effectively pre-process these signals.

The most important signal for our purpose is EDA- electrodermal activity which is extracted from the WESAD dataset where the researchers conducted several experiments on 12 individuals. In these experiments they simulated a stressful state following the *TSST* method and collected a handful of physiological data in the form of various signals. They used a chest-worn and wrist-worn device to do so and collected multiple readings from each individuals. We are considering readings from both these devices for our purpose.

### EDA signals

To summarize theories in [7], EDA measures the *emotional arousal* we experience when we are stressed, fearful, happy and various other emotional states. It is possible to do so because whenever we experience emotional stimulation, sweat glands on our skin secrete sweat causing changes in the skin's electrical conductivity. These electrical changes are indicative of our levels of arousal measured as either skin potenstial, resistance, conductance etc. EDA is measured in microSiemens(μS) .This signal enables us to access to the otherwise autonomously controlled nervous system of the body to detect emotional arousal that can be translated to emotional states offering us an unadulterated view to our own psychological processes in a completely non invasive way.

As studied from [8], EDA or GSR signals consist of two main components that are indicative of our emotional behaviour. 

1. SCL - skin conductance level
2. SCR - skin conductance response

They are dubbed as the *level of the signal* and the *response of the signal* for ease on understanding. The skin conductance level is also referred as the *tonic* component of the signal. It slowly changes over time. The time scale is usually of tens of seconds to tens of minutes. It is not particularly informative on its own. It is shown that tonic level varies widely from person to person as it depends on their hydration, skin dryness etc. Therefore vast majority of professionals and researchers have deemed it to be a poor measure of skin's conductance. The other component, skin conductance response is of particular importance to us. It is also known as the *phasic* component. They are shown as GSR bursts or peaks if a graph of their measure is plotted against time. This phasic component is sensitive to specific stimulus that are emotionally arousing. They occur when EDA amplitudes cross a certain threshold value in a time period within 1-5 seconds after a stimulus is initiated. On a graph of raw EDA signals this phasic component is etched on top of the seemingly unchanged tonic component as shown in figure 1.

![Graph of GSR amplitudes vs Time](https://user-images.githubusercontent.com/24827548/94520735-97a7e700-024e-11eb-8270-3d68fef0a4f2.png)

### EDA and it's relevance to psychoanalysis 

EDA also known as GSR signals, is a property of the human body which shows continuous variation in the electrical characteristics of the skin. These changes in the skin can be triggered by external factors or internal factors in the human body which is why this signal is of great interest to us.  Various studies [3] show that the nervous system is connected to the sweat glands on our skin. These glands secrete sweat in response to external or internal stimuli which causes changes in the skin's electrical conductivity [5]. Therefore we can use skin conductance to reflect and measure cognitive and sympathetic responses. As a result emotional states like stress, happiness and sadness can be detected using EDA. Lastly owing to the fact that measuring EDA is relatively affordable, easy to operate and non-invasive it has been widely used in the field of psychoanalysis and various psychological research.

### Related studies where EDA measures various psychological states

According to [5], EDA is one of the earliest signals to be used for quantifying emotional excitement. In [2], the researchers bring forth an extensive system which analyses human emotional arousal with the help of EDA. EDA was also used to measure stress, where an open source tool was proposed which was able to predict stress with an accuracy of 92% in [4]. It is also used in the field of virtual reality where the researchers used kernel based extreme-learning machine [6] to classify different levels of stress in an environment which simulated stressful conditions, achieving 95% accuracy. These are just a few examples of the vast area of research that is ongoing in the field of psychoanalysis and undoubtedly EDA plays a huge role in it.

### EDA signal processing

For analysing these EDA signals, we will mainly focus on the *Event-related SCRs*  as it is indicative of sudden changes in emotions. For instance when visualized, these SCRs would show peaks in a graph if the user is emotionally aroused in response to some stimulus. We can characterize SCRs with four different metrics: latency, peak amplitude, rise time and recovery time, their explanations are omitted for sake of brevity. However our focus is on the problems that arise on when analysing these signals. It is seen that EDA signals are not exactly flat before and after a peak and the peaks often appear consecutively hindering analysis. Therefore the signal needs to undergo some preprocessing for classification.

1. Downsampling - we did not apply downsampling here as the data points are already sampled at 4Hz. This sampling rate was appropriate for analysis.
2. Filtering - We had to apply *median filter* to separate the tonic signals from the data as they are non-indicative of emotional arousal. The median filter smoothes the signals leaving the desired phasic signals.
3. Peak detection - we applied built-in algorithms in the neurokit2 python package for automating this task.

### Feature extraction

For preliminary purposes, we are interested in the statistical features of EDA namely Number of GSR peaks, mean peak amplitutde and mean peak magnitude.



































