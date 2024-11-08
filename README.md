Project Report: Mood-Based Music Generation
1. Introduction
Mood-based music generation is an innovative application in which a user’s mood is detected through facial expressions, and music is recommended accordingly. This project applies deep learning to classify moods and associate them with specific music, enhancing user experience by personalizing playlists.

2. Objective
The primary goal of this project is to detect a user's mood from facial images and generate music recommendations matching the mood.

3. Dataset and Preprocessing
Dataset: The project uses a dataset with labeled mood categories (e.g., happy, sad, angry) stored in directories for training and testing.
Preprocessing: Images are resized to 48x48 pixels, normalized, and augmented through rotation, zooming, shifting, and flipping to improve model generalization.
4. Model Architecture
Two models were implemented for mood detection:

Custom CNN Model: Consists of three convolutional blocks, each followed by batch normalization and dropout, and a fully connected layer ending with a softmax output.
ResNet50V2 Transfer Learning Model: A ResNet50V2 model is fine-tuned on mood data, with most layers frozen except the last 50. This pre-trained model provides robust feature extraction, enhancing mood classification accuracy.
5. Training and Evaluation
The models were trained with 30 epochs, using:

Early Stopping: To halt training if validation accuracy did not improve, preventing overfitting.
Learning Rate Reduction: Adjusts the learning rate when validation loss plateaus.
Evaluation on test data yielded a test accuracy of around 85%, indicating reliable performance in mood detection.

6. Mood-to-Music Mapping
A CSV file containing songs tagged with moods (e.g., happy, sad, energetic) was used. Upon detecting a mood, the system filters and retrieves songs with matching mood tags, enabling a mood-based music recommendation.

7. Results and Discussion
Model Performance: The ResNet50V2 model outperformed the custom CNN model in both accuracy and robustness. Test accuracy reached approximately 85%, with a confusion matrix showing accurate classification across most mood categories.
Future Improvements: Including a wider range of moods and integrating a dynamic playlist generator could further personalize recommendations.
8. Conclusion
This project successfully demonstrates mood detection from facial expressions and mood-based music recommendation. Future enhancements could include real-time mood tracking.

