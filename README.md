# Face-Swap-with-Diffusion
This project was conducted as a part of my assignment for a Deep Learning Internship. It explains the code, implementation as well as the challenges faced and future works on it. The repository contains the code and the attempted output.

The file conatins a code that implements a face-swapping task using a diffusion model, specifically designed to integrate a face image into another image (usually of a human body) while maintaining a natural appearance.

# Importing Libraries:
- torch: A powerful library for deep learning, which is used here to utilize the Stable Diffusion model.
- StableDiffusionInpaintPipeline: A class from the transformers library that provides an interface to the Stable Diffusion model, which is used for inpainting tasks (filling in parts of an image).
- PIL.Image: Used for image processing and manipulation.
- numpy: A library for numerical operations, useful here for image manipulation.
- cv2: OpenCV for additional image processing (though not heavily used in this particular code).
- skimage: Another image processing library, providing a different way to load images.
- matplotlib.pyplot: Used for displaying images.

# Loading the Images:
- load_images: This function takes two file paths (the source face and the target body image), loads them, and ensures they are in RGB format for proper processing.
- convert("RGB"): Ensures that the images are in the correct color format.

# Preprocessing the Images:
- preprocess_images: The function resizes and aligns the face image to match the size and position of the face in the target body image.
- target_body_np: Converts the target body image to a NumPy array for easy manipulation.
- face_position: Specifies where on the target image the face should be placed.
- resized_face: Resizes the face to fit the intended region on the target image.

# Applying the Diffusion Model:
- apply_diffusion_model: This function uses the diffusion model to perform the inpainting task.
- StableDiffusionInpaintPipeline: A specific pipeline for inpainting, which is loaded with a pre-trained model ("CompVis/stable-diffusion-v-1-4").
- pipe.to("cuda"): Moves the pipeline to the GPU for faster computation.
- mask: A binary mask is created to indicate the region where the face will be swapped. Only this region will be modified by the model.
- output: The output from the model, which is the inpainted image with the face swapped.

# Blending the Images:
- blend_images: This function combines the output of the diffusion model with the original target body image.
- blended_image: The final image, where the face has been seamlessly integrated into the target body.

# Main Function:
- main: This is the main function where all the previous functions are called in sequence to complete the face-swapping task.
- final_image.save("output_face_swap.jpg"): Saves the final output image to a file.
- final_image.show(): Displays the final image.

# Key Points:
- Face Positioning: The face_position tuple is critical in determining where the face will be placed on the target image. This needs to be adjusted depending on the specific images used.
- Model Choice: The diffusion model used is crucial for quality. The code uses "CompVis/stable-diffusion-v-1-4," which is a specific variant of the Stable Diffusion model.
- Blending Process: The blending step ensures that the face is integrated smoothly into the target image, avoiding harsh edges or unnatural appearances.

# Challenges faced
- Incorrect positioning of the intended image that was to be replaced with
- personal grievance- had little knowledge about Diffusion or any other model related to Face swapping ( had to resort to use ChatGPT for code clarification)

# Future Works
- Attempt to attain the correct positioning so as to achieve the face swap.

