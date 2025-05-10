## Quick guide for colab

- This guide allows you to use my code in google colab without mounting google drive and use hidden secrets.

Add the following lines at the start

```
!pip install PyPDF2
!pip install langchain-community
!pip install faiss-cpu
!pip install groq
```

### Edit Secrets

Open the secrets tab to the left and enter the secrets from the dotenv file.

![image](https://github.com/user-attachments/assets/16c7e28b-96a3-4164-b246-796081b9f380)


### Replace dotenv imports
instead of reading the keys from a .env file read them from colab directly:

```
from google.colab import userdata
google_api_key = userdata.get('GOOGLE_API_KEY')
openai_api_key = userdata.get('OPENAI_API_KEY')
groq_api_key = userdata.get('GROQ_API_KEY')
```

### Upload data to Colab

Open the data tab on the left side and upload your files to the temporary storage:
![image](https://github.com/user-attachments/assets/02fb94e8-d2b8-4b27-a2c6-ae00e98f0a24)

### Adjust path in the notebook:

```
glob_path = "/content/*.pdf"
```

Note that you can also create your faiss folder to store the vector store in the temporary location. If you want to do it forever, you need to mount google drive.
