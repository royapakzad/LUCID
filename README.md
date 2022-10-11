# Bias Detection in Perspective API
for Stanford HAI audit competition

#### Check out the code in [perspective_public.ipynb](https://github.com/royapakzad/hai_perspective_api/blob/main/perspective_public.ipynb)

#### Google form for writing "seed" sentences: https://forms.gle/UxMKueg6NTJDYoaw7

#### outputs in [output_religion.csv](https://github.com/royapakzad/hai_perspective_api/blob/main/output_religion.csv) and [output_derogatory.csv](https://github.com/royapakzad/hai_perspective_api/blob/main/output_derogatory.csv)

The proposed project will use “community-based red teaming” to test for biases in Perspective API, a popular service used by media platforms that seeks to combat online harassment and toxicity. In the initial test case, religious biases are the focus, but the concept can be readily expanded to encompass other forms of bias (gender-based, ethnic, national, etc). 

[Perspective API] (https://perspectiveapi.com/) is a project developed by Google Jigsaw and Google’s Counter Abuse Technology Team to evaluate the toxicity of online comments on third-party websites. In this context, “toxicity” is defined by Perspective as "a rude, disrespectful, or unreasonable comment that is likely to make someone leave a discussion." Perspective API matters because it is one of the most widely used tools used by publishers and platforms for moderating online discussions. Current users of the API include Reddit, the New York Times, Le Monde, and the Wall Street Journal.

The key advantage of the Global Perspectives approach is ease of use and its use of emphasis on community-focused auditing. Many worthy projects currently exist which seek to assess bias on online platforms, but because they are directed by professionals, they often run up against problems when it comes to practical implementation: inevitably, there will be a gap between the “insiders” involved in red teaming or bounty programs and the global community of users who on any given platform. By utilizing an input method with a very low barrier to entry and wide adoption (Google Forms) the proposed project aims to directly draw on insights from the largest possible range of affected communities. 

How does the tool work? Using the repository available on hatebased.org, I first collected a large sample of derogatory terms used against various religions. I then set up a simple Google Form template in which users in affected communities can contribute sentences or phrases to test the limits of Perspective API. Finally, I wrote Python code that integrates these components with Perspective API itself. A user-submitted phrase is checked against the API along with alternative variations that feature other derogatory terms, and the toxicity scores are compared. 

Naturally, a great many derogatory terms involving religion are already included in the API. But these terms can change fast, and the global use case of Perspective API means that some faith communities are likely falling through the cracks. The current implementation of Global Perspectives is a preliminary test case that invites users to contribute sentences involving Muslims, but it can readily be expanded. Global Perspective harnesses community input to find edge cases and to surface more esoteric or emergent forms of toxic speech online. 



The end result of this project is twofold. First, it will help Perspective API to refine its model through direct community input. Second, the accumulated submissions will result in a large dataset which can be used in related efforts in the future. An additional benefit is to trial methods of “community-based red teaming,” a technique which can be applied more broadly in other forms of bias detection. 

