# Streamlit Notes
## 1. Installation

### STEP 1
- Create you virtual environment and activate it.
- Install streamlit.
~~~
pip install streamlit
~~~

### STEP 2
-  Verify installation.
~~~
streamlit --version
~~~

### STEP 3
- Create a script and run in.

~~~
streamlit run your_script.py
~~~

## 2. Fundamental Concepts

### (a) Basic concepts
- Running a streamlit script
~~~
streamlit run my_script.py [-- script args]
~~~
- `st.text` - Writes raw text to your app.
- `st.line_chart` - Draws a line chart.
- `st.sidebar` - Side navigation bar drawer.
- `st.title` - Title.
- `st.radio` - Radio buttons
- `st.session_state` - Used to store input and output values.
- `st.markdown` - Used to add the markdown feature the way you normally would in a markdown script.
- `st.text_input` - Accepts text input from user.
- `st.button` - Creates a button.
- `st.write` - Used to write anything from text to tables.
- `st.camera_input` - Adds the camera feature, where the camera will open.
- `st.progress` - 
- `st.success` - 
- `st.warning` - Adds a warning message.
- `st.image` - 
- `st.fle_uploader` - Adds the uploading files feature, and the file type can be specified in the function's argument "type".
- `st.number_input` - Accepts input as numbers.
- `st.error` - Displays an error message.
- `st.slider` - Adds a slider on the page.
- `st.subheader` - 
- `st. pyplot` -
- `@st.catche_data`- A decorator which allows developers to skip certain computations when their apps rerun.
- 