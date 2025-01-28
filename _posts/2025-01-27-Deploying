# Deploying My FastAI Model: Challenges and Lessons Learned 🚀🤖

After completing Chapter 2 of the FastAI course, I was excited to deploy my model into an application. The idea was to transform the model into a fully functioning app, hosted on **Hugging Face Spaces**, to classify images seamlessly. My journey involved tools like **Kaggle Notebooks**, **Visual Studio Code**, **Bash**, **Gradio**, and **Hugging Face Spaces** to achieve this. However, the road to deployment was far from smooth, and I encountered several unexpected challenges. Here’s a detailed account of the issues I faced, the solutions I tried, and where I stand today.

---

## The Goal 🎯  
The goal was to deploy my **image classification model**, which I built in Kaggle Notebooks using FastAI. After training and evaluating the model, I exported it and created an interactive app using **Gradio**. I planned to host the app on **Hugging Face Spaces**, making it accessible to users worldwide. To manage the process, I used **Visual Studio Code** for coding and debugging and **Bash** for executing commands. Everything was designed to be simple, efficient, and effective—until the errors started to surface. 😅

---

## The Challenges 🛠️  
While setting up my environment and running my application, I encountered several major issues. Here’s a summary:

### 1. **ModuleNotFoundError for FastAI and Related Libraries**  
   - Despite installing FastAI via `pip install fastai`, errors persisted stating that the module could not be found.  

### 2. **Binary Compatibility Issues**  
   - Errors like `ValueError: numpy.dtype size changed, may indicate binary incompatibility` suggested compatibility issues between numpy and other dependencies.  

### 3. **Dependency Build Failures**  
   - Some dependencies failed to build with pip, displaying errors related to setuptools and pkg_resources.  

### 4. **Python Version Conflicts**  
   - Using Python 3.12 caused compatibility issues with FastAI and other libraries.  

### 5. **Environment Isolation Problems**  
   - Even with a virtual environment, errors persisted across installations.  

---

## Solutions Tried 🛠️✅  
Here’s what I did to address these challenges:

### 1. **Model Creation in Kaggle**  
   - Built and trained the model in **Kaggle Notebooks**, which has pre-installed libraries like FastAI.  

### 2. **Verified Project Setup**  
   - Ensured that my `requirements.txt` included all necessary dependencies:
     ```
     fastai
     torch
     gradio
     duckduckgo-search
     numpy
     pandas<2.0.0
     ```
   - Installed them using:
     ```bash
     pip install -r requirements.txt
     ```

### 3. **Set Up a Virtual Environment**  
   - Created a virtual environment for isolation:
     ```bash
     python3 -m venv venv
     source venv/bin/activate  # Linux/Mac
     venv\Scripts\activate     # Windows
     ```

### 4. **Managed Python Version**  
   - Downgraded to Python 3.10 to resolve compatibility issues:
     ```bash
     sudo apt install python3.10 python3.10-venv python3.10-dev
     python3.10 -m venv venv
     source venv/bin/activate
     pip install -r requirements.txt
     ```

### 5. **Reinstalled Problematic Dependencies**  
   - Reinstalled numpy, pandas, and FastAI:
     ```bash
     pip install --force-reinstall numpy pandas fastai
     ```

### 6. **Workarounds for Pip Build Errors**  
   - Used source installations for dependencies that failed to build:
     ```bash
     pip install --no-binary :all: some_package
     ```

### 7. **Tested Locally with Visual Studio Code**  
   - Ran the app locally to debug:
     ```bash
     python app.py
     ```
   - Tested problematic imports individually:
     ```bash
     python -c "import fastai; import ipywidgets; print('Dependencies installed!')"
     ```

### 8. **Hosted on Hugging Face Spaces**  
   - Deployed the app to Hugging Face Spaces using Gradio but encountered runtime errors due to unresolved dependency issues.  

---

## Current Status 📌  
Despite these efforts, the following issues remain:  
- **ModuleNotFoundError:** Libraries like fastai and ipywidgets throw import errors.  
- **Binary Compatibility Issues:** Errors like `numpy.dtype size changed` persist.  
- **Pip Build Errors:** Some dependencies fail to build wheels.  

---

## The Solution I Found 🙌  
After trying multiple approaches (which I documented earlier), the breakthrough came thanks to a **FastAI student's post** on their forum:  
**Hafiz Ahmad Hassan** wrote about updates for deploying models with Gradio and shared a modified version of Tanishq's tutorial.  

Here’s the key snippet that resolved my issues:  
```python
image = gr.Image(type="pil")
label = gr.Label(num_top_classes=3)

intf = gr.Interface(fn=classify_image, inputs=image, outputs=label).launch(share=True)  

## Big Thanks 🙌  
Big thanks to **Hafiz** for pointing out the updated code and to **Tanishq** for the original tutorial!  
You can check out Tanishq's detailed post [here](https://www.tanishq.ai/blog/posts/2021-11-16-gradio-huggingface.html).  

---

## Current Status 📌  
With this fix, my app is finally up and running on **Hugging Face Spaces**! 🎉  
The deployment process taught me a lot about debugging, dependency management, and the importance of community support.  

---

## Lessons Learned 🌟  
- **Leverage the Community:** Forums and blog posts are gold mines for solving tricky issues.  
- **Stay Updated:** Tutorials and libraries evolve—always check for recent changes.  
- **Simplify Inputs and Outputs:** Gradio's intuitive API made it much easier to debug the deployment process.  

---

## Conclusion ✨  
Deploying a machine learning model is a rewarding but challenging process. Thanks to the help of the **FastAI community** and Hafiz’s timely post, I’ve successfully deployed my app. Stay tuned as I share more learnings and experiences! 🎉  
