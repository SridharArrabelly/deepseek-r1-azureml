# DeepSeek R1 serving with Azure ML

This is a simple example of how to serve a DeepSeek model with Azure ML.

## How to get started

### If you are using Azure ML Studio
1. Create your compute instance. For code development, we recommend `Standard_DS11_v2` (2 cores, 14GB RAM, 28GB storage, No GPUs).
2. Open the terminal of the CI and run:
    ```shell
    git clone https://github.com/daekeun-ml/deepseek-r1-azureml.git
    conda activate azureml_py310_sdkv2
    pip install -r requirements.txt
    ```
3. Modify the **`config.yml`** file with your Azure ML workspace information.
4. You can deploy the model to Azure ML using vLLM or SGLang.
- **vLLM**: Run the notebook **`deepseek_aml_serving_vllm.ipynb`**
- **SGLang**: Run the notebook **`deepseek_aml_serving_sglang.ipynb`**


### If you are using your own local environment
1. Open the terminal of the CI and run:
    ```shell
    git clone https://github.com/daekeun-ml/deepseek-r1-azureml.git
    pip install -r requirements.txt
    ```
2. Modify the **`config.yml`** file with your Azure ML workspace information.
3. You can deploy the model to Azure ML using vLLM or SGLang.
- **vLLM**: Run the notebook **`deepseek_aml_serving_vllm.ipynb`**
- **SGLang**: Run the notebook **`deepseek_aml_serving_sglang.ipynb`**

## References

## Requirements
Before starting, you should meet the following requirements:

- [Access to Azure OpenAI Service](https://go.microsoft.com/fwlink/?linkid=2222006)
- [Azure ML getting started](https://github.com/Azure/azureml-examples/tree/main/tutorials): Connect to [Azure ML] workspace and get your <WORKSPACE_NAME>, <RESOURCE_GROUP> and <SUBSCRIPTION_ID>.
- [Azure AI Studio getting started](https://aka.ms/azureaistudio): Create a project

- ***[Compute instance - for code development]*** A low-end instance without GPU is recommended: **[Standard_E2as_v4] (AMD 2 cores, 16GB RAM, 32GB storage) or **[Standard_DS11_v2]** (Intel 2 cores, 14GB RAM, 28GB storage, No GPUs)  
- ***[Compute cluster - for SLM/LLM fine-tuning]*** A single NVIDIA A100 GPU (**[Standard_NC24ads_A100_v4]**) is recommended. If you do not have a dedicated quota or are on a tight budget, choose **[Low-priority VM]**.
- ***[SLM/LLM deployment]*** At least 1 NVIDIA A100 GPU (**[Standard_NC24ads_A100_v4]**) is required.

## License Summary

This sample code is provided under the MIT-0 license. See the LICENSE file.