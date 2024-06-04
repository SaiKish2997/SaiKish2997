import openai
import os

from langchain_openai import openAI
from langchain_core.prompts import PromptTemplate
from langchain.chains import LLMChain

"

if openai.api_key.startswith("sk-"):
    llm = openAI(temperature=0.8)

    def generate_names_for_kids(names_generating,baby_dob):
        prompt_template_name=PromptTemplate(
        input_variables=['names_generating','baby_dob'],
        template=("we have delivered a bby suggest me a beautifulname {names_generating},and the his birthday is coming{baby_dob}, so i req everyone ")
        
    ),
        name_chain= LLMChain(llm=llm,prompt=prompt_template_name)
        response= name_chain({'names_generating':names_generating})
        return response

else:
    print("please provide a valid key")


if __name=='__main__':
    print(generate_names_for_kids("boy baby"))

