# ComfyUI Serverless Deployment

This repository contains a Docker configuration for running a ComfyUI workflow with the flux-schnell model and RealESRGAN_x2 upscaler in a serverless environment.

## Included Components

- **Base Image**: RunPod ComfyUI worker (5.1.0-base)
- **Custom Nodes**: KJNodes
- **Models**:
  - flux1-schnell-fp8.safetensors (FLUX1 checkpoint)
  - RealESRGAN_x2.pth (upscaler)

## Workflow

This Docker image is designed to run the "flux-schnell-RealESRGAN_x2" ComfyUI workflow. The workflow leverages the FLUX1 model for image generation and the RealESRGAN_x2 upscaler for enhancing the output quality.

## Usage

### Local Development

To build and run the Docker image locally:

```bash
# Build the Docker image
docker build -t comfyui-flux-schnell .

# Run the container
docker run -p 8188:8188 comfyui-flux-schnell
```

### Deploying on RunPod

1. Push this repository to your GitHub account
2. Create a new RunPod template using this repository URL
3. Deploy a new pod using the template
4. Access the ComfyUI interface through the exposed port (typically 8188)

## Docker Details

The Dockerfile:
- Uses the RunPod ComfyUI worker as a base image
- Installs KJNodes custom nodes
- Downloads the flux1-schnell-fp8 model
- Downloads the RealESRGAN_x2 upscaler model

## Development

To modify this setup:

1. Update the Dockerfile to include additional models or custom nodes
2. Build and test locally
3. Push changes to this repository
4. Redeploy your RunPod instance

## License

Please respect the licenses of all included models and software.

- FLUX1 model: [License Information](https://huggingface.co/Comfy-Org/flux1-schnell)
- RealESRGAN: [License Information](https://huggingface.co/ai-forever/Real-ESRGAN)