# DeepSeek R1 serving with Azure ML

This is a simple example of how to serve a DeepSeek model with Azure ML.


## How to get started

1. Create your compute instance. For code development, we recommend `Standard_DS11_v2` (2 cores, 14GB RAM, 28GB storage, No GPUs).
2. Open the terminal of the CI and run:
    ```shell
    git clone https://github.com/daekeun-ml/deepseek-r1-azureml.git
    conda activate azureml_py310_sdkv2
    pip install -r requirements.txt
    ```
3. Modify the **`config.yml`** file with your Azure ML workspace information.
4. Run the notebook **`deepseek_aml_serving_vllm.ipynb`** to deploy it to Azure ML.

## References


## Requirements
Before starting, you should meet the following requirements:

- [Access to Azure OpenAI Service](https://go.microsoft.com/fwlink/?linkid=2222006)
- [Azure ML getting started](https://github.com/Azure/azureml-examples/tree/main/tutorials): Connect to [Azure ML] workspace and get your <WORKSPACE_NAME>, <RESOURCE_GROUP> and <SUBSCRIPTION_ID>.
- [Azure AI Studio getting started](https://aka.ms/azureaistudio): Create a project

- ***[Compute instance - for code development]*** A low-end instance without GPU is recommended: **[Standard_E2as_v4] (AMD 2 cores, 16GB RAM, 32GB storage) or **[Standard_DS11_v2]** (Intel 2 cores, 14GB RAM, 28GB storage, No GPUs)  
- ***[Compute cluster - for SLM/LLM fine-tuning]*** A single NVIDIA A100 GPU (**[Standard_NC24ads_A100_v4]**) is recommended. If you do not have a dedicated quota or are on a tight budget, choose **[Low-priority VM]**.
- ***[SLM/LLM deployment]*** At least 1 NVIDIA A100 GPU (**[Standard_NC24ads_A100_v4]**) is required 

**Note**
For managed online endpoints, [Azure ML reserves 20% of the quota for the deployment].[^1] If you request a given number of instances for those VM SKUs in a deployment, you must have a quota for `ceil(1.2 × number of instances requested for deployment) × number of cores for the VM SKU` available to avoid getting an error. For example, if you request 1 instances of a `Standard_NC6s_v3` VM (that comes with six cores) in a deployment, you should have a quota for 12 cores (ceil(1.2 × 1 instances) = 2, 2 × 6 cores) available.  

## License Summary

This sample code is provided under the MIT-0 license. See the LICENSE file.