1. What are the shapes (sizes) of `x_train`, `x_val`, and `x_test`?

The shapes (sizes) of x_train, x_val, and x_test are:
x_train: (48000, 28, 28)
x_val: (12000, 28, 28)
x_test: (10000, 28, 28)

2. What do the shapes (sizes) of `x_train`, `x_val`, and `x_test` represent?

The first number is the number of samples,the last two numbers (28, 28) are the pixel dimensions of each image.

3. What are `y_train`, `x_val`, and `y_test` for?

y_train:labels for the training set;x_val:Input data for the validation set;y_test: Labels for the test set.

4. How would you modify the code if you wanted to use a different dataset provided by `keras.datasets`, such as `fashion_mnist`?

'(x_train_loaded, y_train_loaded), (x_test, y_test) = tf.keras.datasets.fashion_mnist.load_data().'

5. If the MNIST images are grayscale, what would you expect the range of pixel values to be?

The expected range of pixel values for grayscale MNIST images is typically 0-255.

6. Explain the significance of the 80-20 split when creating a validation set. Are there scenarios where you might choose a different split?

The ratio can be adjusted based on dataset size and problem complexity.

7. What kind of data does the MNIST dataset contain, and why is it commonly used in machine learning and deep learning courses?
# I asked AI about this:
Contains grayscale images of handwritten digits (0-9), widely used because: 
1.Manageable scale, easy to process.
2.Simple and well-defined problem.
3.Widely used, facilitates comparison between different algorithms.
4.Suitable for learning introductory machine learning concepts.




1. How do we plot the last image instead of the first image?

   Replace the "0" in 'img = x_train_np[indices[0]]' with "-1".

2. Which handwriting digit image do we have the most in the dataset?

number "1".

3. Which handwriting digit image do we have the least in the dataset?

   number "5"

4. How can we modify the code to display three images for each digit side by side?

（See the codes down below)

5. How would you adjust the code to display the images in a 10x1 grid (10 rows and 1 column) instead of a 5x2 grid?

Change ‘plt.subplot(5, 2, i + 1)’, to 'plt.subplot(10, 1, i + 1)'.

6. Why do we use cmap='gray' when displaying the images? What happens if you remove it?

   The MNIST dataset contains grayscale images of handwritten digits. Each pixel in these images is represented by a single value, typically ranging from 0 (black) to 255 (white), with values in between representing shades of gray.
When we use cmap='gray', we're telling matplotlib to use a colormap that maps these single values to shades of gray. This ensures that the images are displayed as true grayscale images, which is how they were originally captured and how they're meant to be viewed.

7. How can we modify the code to display the average image of each digit (i.e., the mean pixel value for each position)?

Maybe add 'avg_img = np.mean(digit_images, axis=0)' before the displaying the image.

8. Why might it be essential to know which handwriting digit images are most or least common in the dataset?

If some digits are significantly under- or over-represented in the dataset, it can lead to class imbalance. And might create bias towards predicting the more common digits in the models.





1. What is the value of `x_train.max()`, and why are we printing it?

   It's 1, to check the normalization of the preprocessed training data, normalization is a crucial step in machine learning because it brings all data and features to a similar scale, ensuring no single feature dominates due to its larger magnitude.

2. What would the x_train.min() value be after preprocessing? Explain why.
 
 It would be 0, since the most common normalization technique for image data is to scale the pixel values from their original range [0, 255] to [0, 1]. 

3. How is the shape of `y_train`, `y_val`, and `y_test` different from before the preprocessing step?

The labels are now likely in a 2D array.Each row represents one sample, and each column represents a distinct class.The shape is now probably (n_samples, n_classes), where n_classes is the total number of unique classes.

4. How is the One-Hot vector representing the label for each data?
   
   Each one-hot vector represents a label by having a '1' in the position corresponding to the correct class and '0's everywhere else, uniquely identifying the class for each data point.

5. How is the normalization achieved for the image data?

Through the preprocess() function:orginal image/ 255.

6. Why do we need to reshape the image data for CNNs and not just use the flattened version like in MLPs?
   
   CNNs require reshaped image data to preserve spatial relationships between pixels, enabling them to detect and learn hierarchical features effectively, unlike MLPs which process flattened inputs.

7. Why is applying the same preprocessing steps to training and testing datasets important?

For maintaining consistency and ensuring that the model generalizes correctly.

8. Given that the MNIST dataset consists of ten digits (0-9), what is the expected size of the one-hot encoded vector for the labels? Why?
    
The expected size is "10": 10 possible digits (0-9), with a '1' in the position of the correct digit and '0's elsewhere.




1. What can you infer about the output map as the CNN layers progress towards the output?

 Increasing feature abstraction:Shallow layers capture simple features (like edges, textures).Deeper layers combine these simple features to form more abstract, complex representations.

2. Do the images from the CNN layers seem to capture the higher-order feature? If so, what?

It does, it progressively transforms low-level, localized features into high-level, abstract representations that are more relevant to the task at hand, while reducing spatial dimensions and increasing feature complexity.