# AnnoLLM

This repo hosts the data for our NAACL 2024 paper "[**AnnoLLM: Making Large Language Models to Be Better Crowdsourced Annotators**](https://arxiv.org/abs/2303.16854)".

## ConIR Dataset

The conversation-based information retrieval (ConIR) dataset is created by ChatGPT based on the MS-MARCO passage ranking dataset. 
The *ConIR* dataset is available at https://huggingface.co/datasets/He-Xingwei/ConIR. The sizes of the training and test sets for ConIR are 71,557 and 3,000 respectively.

When using it, please adhere to the MIT license. 

Below is one example of the data:

```json
{
    "query": ["what is tonic water?"], 
    "pos_p": [4491229], 
    "conversation": "P1: What is tonic water?\nP2: Tonic water is a carbonated soft drink that contains quinine, which gives it its distinctive bitter taste.\nP1: What is quinine?\nP2: Quinine is a bitter alkaloid that is extracted from the bark of the cinchona tree.\nP1: Why is tonic water bitter?\nP2: The quinine in tonic water gives it its distinctive bitter taste.\nP1: What is tonic water used for?\nP2: Tonic water was originally developed as a way to prevent malaria, but is now primarily consumed as a mixer for cocktails.\nP1: Can you give me an example of a cocktail that uses tonic water?\nP2: Gin and tonic is a popular cocktail that uses tonic water.\nP1: Is tonic water only used in cocktails?\nP2: No, tonic water can also be consumed on its own, although it is often considered too bitter to drink without the addition of sweeteners.\nP1: Is tonic water still used to prevent malaria?\nP2: While quinine has been shown to be effective against malaria, tonic water is now primarily consumed as a mixer for cocktails and is not commonly used for its medicinal properties.\nP1: Is tonic water only found in Australia?\nP2: No, tonic water is available in many countries around the world. It is not specific to Australia.\nP1: Can you tell me more about the Great Barrier Reef?\nP2: The Great Barrier Reef is the world's largest coral reef system, located in the Coral Sea off the coast of Australia. It is a UNESCO World Heritage Site and is considered one of the seven natural wonders of the world. It is also an important economic resource for Australia.\nP1: What kind of marine life can be found on the Great Barrier Reef?\nP2: The Great Barrier Reef is home to over 1,500 species of fish, 400 species of coral, and 4,000 species of mollusks.", 
    "neg_p": [7120024, 7165296, 3673008, 2964233, 8086308, 1513810, 2364054, 3436519, 8094542, 7966688, 8537198, 4642397, 3510228, 4765344, 2214087]
}

```

| **Attribute** | **Type** | **Description**                                              |
| ------------- | -------- | ------------------------------------------------------------ |
| query   | List[String]   | Each query is extracted from MS-MARCO.                                               |
| pos_p      | List[Integer]   | Ids of the positive passages for the queries/conversation.                                            |
| conversation        | String   | The conversation is generated by ChatGPT based on positive passages.                                                 |
| neg_p      | List[Integer]   | Ids of the negative passages for the queries/conversation.                                                |

Passages are available in the collection.tsv (https://msmarco.z22.web.core.windows.net/msmarcoranking/collection.tar.gz) file. 
