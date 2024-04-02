# Image Upscaling and Generation Documentation

## Introduction
This documentation outlines the process and parameters used for image generation and upscaling. The provided code utilizes different models and libraries for generating and upscaling images, with a focus on achieving realistic and high-quality results. The document will cover the software requirements, model parameters, and execution instructions for running the code on both Google Colab and local machines.

## Software Requirements
To run the provided code successfully, ensure that the following software dependencies are installed:

1. Python (>=3.6)
2. PyTorch
3. Transformers
4. Accelerate
5. Diffusers
6. Xformers
7. Vulkan 

For convenience, you can install these dependencies using pip, as demonstrated in the code snippet below:

```bash
pip install diffusers["torch"] transformers accelerate xformers
```

Additionally, for local execution, ensure that Vulkan is installed. Vulkan is a low-overhead, cross-platform 3D graphics and computing API.

## Model Information
The image generation and upscaling process utilize two different models:

1. **Absolute Reality**: This model is employed for generating realistic images based on the provided prompt. It's noteworthy that generating human images requires specific considerations, such as maintaining a proper height-to-width ratio to avoid distortion. The key parameters for this model include:
   - `prompt`: Actual prompt for generating images.
   - `negative_prompt`: Defines mistakes to avoid during image generation.
   - `num_inference_steps`: Number of inference steps during image generation.
   - `guidance_scale`: Determines the extent to which the resulting image is guided by the prompt.
   - `height` and `width`: Dimensions of the generated image.
   - `generator`: Seed value for generating consistent outputs.

2. **Real-ESRGAN-W-Ultrasharp4x**: This model is utilized for upscaling images, providing sharper and more detailed results. The parameters for this model include:
   - `-s scale`: Upscale ratio (can be 2, 3, or 4).
   - `-i input-path` and `-o output-path`: Input and output paths for image files.
   - Other optional parameters for multi-GPU processing and verbose output.

## Execution Instructions
### Google Colab
1. Execute the provided code in a Google Colab notebook environment.
2. Ensure that all necessary dependencies are installed using the `pip install` commands provided.
3. Run the code cells sequentially to generate and upscale images.
- Warning: The Upscaler only goes upto 95.83% on google colab but only local machine It works perfectly 
### Local Machine
1. Ensure that Python and required libraries are installed, including Vulkan for GPU acceleration.
2. Clone the Real-ESRGAN-W-Ultrasharp4x repository from GitHub.
3. Download the pre-trained model for Real-ESRGAN-W-Ultrasharp4x.
4. Extract the downloaded model files.
5. Execute the provided code snippet, ensuring that paths to input and output images are correctly specified.
6. Adjust the parameters as needed for different upscale ratios or other options.

### Note
- While the code can be executed on both Google Colab and local machines, it's essential to consider hardware constraints. The provided information suggests that the upscaler runs faster on the local machine due to compatibility with Vulkan.
- Careful attention should be paid to image dimensions, particularly when generating human images, to avoid distortion and duplication.
- The resolution of the generated images may not exactly match the specified dimensions due to constraints imposed by the image generation model (Absolute Reality)
- The Upscaler only goes upto 95.83% on google colab but on local machine It works
perfectly 
### Example Images


![generated_img8](https://github.com/iamFury2K/docs/assets/73428754/13245e8b-1ee8-45b6-ac99-b7cda319afb7)
![generated_img7](https://github.com/iamFury2K/docs/assets/73428754/d7047437-1589-4bd4-9651-5c79b3c0a6c2)
![generated_img5](https://github.com/iamFury2K/docs/assets/73428754/6215c4ee-2c1e-4328-b033-7d2908469e1a)
![generated_img4](https://github.com/iamFury2K/docs/assets/73428754/c91b0f7b-a2db-48e0-a519-0661eb4fa296)
![generated_img3](https://github.com/iamFury2K/docs/assets/73428754/c16cc7d1-3166-4127-9dbb-5c40f91b2586)
![generated_img2](https://github.com/iamFury2K/docs/assets/73428754/3bca6ba1-b302-4b35-9f8b-4fdcfb0c7809)
![generated_img1](https://github.com/iamFury2K/docs/assets/73428754/616214d0-4112-4fd6-88e9-e905e1cda245)








