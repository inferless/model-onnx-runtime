# Model-Onnx
In this template we will import a model.onnx file, which is uploaded to a cloud URL.

## Quick Start
Here is a quick start to help you get up and running with this template on Inferless.

### Create a Custom Runtime in Inferless
To access the custom runtime window in Inferless, simply navigate to the sidebar and click on the Create new Runtime button. A pop-up will appear.

Next, provide a suitable name for your custom runtime and proceed by uploading the **runtime.yaml** file given above. Finally, ensure you save your changes by clicking on the save button.

### Import the Model in Inferless
Log in to your inferless account, select the workspace you want the model to be imported into and click the Add Model button.

Select the ONNX as the framework and choose File -> Local File as the import type. In the Step 3, give a suitable name for your model, select url and give the publicily accessible URL for your model.

Use the below public link for the model  https://inferless-public.s3.amazonaws.com/model.zip

Enter all the required details to Import your model. Refer [this link](https://docs.inferless.com/integrations/github-custom-code) for more information on model import.

The following is a sample Input and Output JSON for this model which you can use while importing this model on Inferless.

### Input
```json
{
  "inputs": [
    {
      "data": [
        [
          "Your sample text here"
        ]
      ],
      "name": "input",
      "shape": [
        1,
        1
      ],
      "datatype": "BYTES"
    }
  ]
}
```

### Output
```json
{
  "outputs": [
    {
      "data": [],
      "name": "variable",
      "shape": [
        1,
        -1
      ],
      "datatype": "FP32"
    }
  ]
}
```

---
## Curl Command
Following is an example of the curl command you can use to make inference. You can find the exact curl command in the Model's API page in Inferless.
```bash
curl --location '<your_inference_url>' \
          --header 'Content-Type: application/json' \
          --header 'Authorization: Bearer <your_api_key>' \
          --data '{
            "inputs": [
              {
                "data": [
                  [
                    "Your sample text here"
                  ]
                ],
                "name": "input",
                "shape": [
                  1,
                  1
                ],
                "datatype": "BYTES"
              }
            ]
          }'
```

For more information refer to the [Inferless docs](https://docs.inferless.com/).
