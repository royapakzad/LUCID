# LUCID: Language Model Co-auditing through Community-based Red Teaming

### Finalst at Stanford HAI's AI Audit Challenge: check it out [here](https://hai.stanford.edu/ai-audit-challenge-2023-finalists)

#### The code is available at [LUCID.ipynb](https://github.com/royapakzad/LUCID/blob/main/LUCID.ipynb)

"LUCID" is an AI bias assessment tool that uses a variety of large language models (LLMs) to "red team" AI bias issues. Its primary objectives are to automate certain aspects of AI bias red teaming, to foster a participatory and community-based approach to auditing AI systems, and to provide a platform for documenting, identifying and discussing instances of bias in text. This tool is intended for both AI policy researchers and members of the general public, enabling comparisons across various systems and protected groups. Marginalized communities, who have long been disproportionately affected by discriminatory outcomes related to algorithmic decision-making tools, stand to benefit significantly from this tool as it empowers them to audit these algorithms themselves, document their findings, and hold companies to account.

LUCID represents a significant methodological advancement in this domain because it uses semi-automated "prompt engineering" and community-based red teaming to enhance bias detection over a range of large language models. The tool leverages prompt engineering to automatically generate and compare diverse texts across protected categories and evaluate the potential biases and harms of AI language models. The tool can generate texts that cover a wide variety of scenarios and perspectives, and then use APIs to rapidly compare the outputs of multiple LLMs.

The tool presently focuses on comparing protected categories such as race, gender, religion, and nationality. However, I intend to expand these categories to include language and occupation. At present, LUCID utilizes two available APIs: OpenAI’s GPT-3 and Perspective API (which is not an LLM, but a machine learning model which assesses “toxic” language). However, as new APIs become available (such as those for LLMs developed by Anthropic, Google, Meta, and Microsoft) LUCID can easily be modified to integrate them in its analysis. The tool is scheduled to be piloted at RightsCon 2023 and FAccT CRAFT (subject to successful application submission) for hands-on workshops.

LUCID operates by importing several libraries and setting up credentials for accessing Google Sheets, Perspective API, and OpenAI API. The script then performs a series of operations on a list of sentences obtained from a [Google Form](https://docs.google.com/forms/d/e/1FAIpQLSfu5u8dWCJU69v7RnqaYmHQxKlkXXq60tMInfMcSrJJ_dNRJA/viewform). It replaces words related to countries, religions, races, and genders in each sentence with alternative words, generates new sentences, and calculates the toxicity score of each new sentence using Perspective API. Next, the script generates text completions for each new sentence using available LLM APIs (which, in terms of current build, means GPT-3), output the word count of each completion and calculates the “controversy scores” for each completion. Word count and “controversy scores” are created to further expose the LLM API's potential indirect biases. Informed by prompt engineering, controversy scores are defined as:

controversy score (male)  is obtained by asking LLM API to use its internal "knowledge", in the persona of a human male, to assess how controversial a figure, person, thing, or group (or a given sentence) is on a scale of 1 to 10, with 10 being something that human male would deem to be most controversial, and 1 least. And controversy score (female)  is obtained by asking LLM API to use its internal "knowledge", in the persona of a human female, to assess how controversial a figure, person, thing, or group (or a given sentence) is on a scale of 1 to 10, with 10 being something that human female would deem to be most controversial, and 1 least.

Finally, the script writes back the sentences, their Perspective API score, prompt completion, their word counts, and controversy scores to a new [Google Sheet](https://docs.google.com/spreadsheets/d/1ji1tzYiQf_XAMdHym1DU4Z-apYDUqxWtH805-5EBjqw/edit?usp=sharing). 

This tool is grounded in the conviction that red teaming should not only be done by experts, but also by affected communities and by the general public. One of the most innovative aspects of the tool, then, is its user-friendliness and low barrier to entry, as it only requires the use of Google Forms and Google Sheets. But though LUCID is simple, it is also a novel approach to a fast-changing field. It is a  tool that can be used at scale and in various bias categories, and the results can be replicated by other users using the same systems, as the code is open source (GitHub page). 

As the use of AI language models continues to grow, tools like this will be essential for ensuring the alignment of AI models with the needs of underrepresented communities  and for promoting critical thinking about bias detection. 

#### Project Presentation: https://drive.google.com/file/d/1PytF6BuFDepyHQjKieNrJ6EMMV-TsRWq/view?usp=sharing

#### Project Slides: https://docs.google.com/presentation/d/1QMQOsodlYFPa5AhOf0pcbDP7McBIHIj63fZjLj_lZg8/edit?usp=sharing

#### Google form for writing "seed" sentences: https://forms.gle/UxMKueg6NTJDYoaw7

#### Outputs in the Google Sheet for identifying, discussing, and documenting biases: https://docs.google.com/spreadsheets/d/1ji1tzYiQf_XAMdHym1DU4Z-apYDUqxWtH805-5EBjqw/edit?usp=sharing 
