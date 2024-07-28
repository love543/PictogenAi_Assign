# PictogenAi_Assign
# Workflow Explanation:
Loading the Model: The StableDiffusionXLInpaintPipeline model is loaded from the pretrained stabilityai repository with specific settings to use half-precision floating point and safe tensors for better performance on CUDA.

Preparing the Image: The original image is loaded and converted to RGB mode to ensure compatibility. A new image canvas is created with 128 extra pixels on each side, and the original image is pasted in the center.

Creating the Mask: A mask is created with white indicating areas to be inpainted and black for the original image area. This mask is used to guide the inpainting process.

Inpainting Process: The inpainting is performed in chunks of 512x512 pixels to manage memory usage. Each chunk is processed separately, and the results are pasted back into the corresponding region of the new image.

Saving the Result: The final outpainted image is saved to the specified path.
