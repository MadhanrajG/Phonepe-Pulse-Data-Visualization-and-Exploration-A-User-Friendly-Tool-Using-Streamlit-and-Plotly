# Phonepe-Pulse-Data-Visualization-and-Exploration-A-User-Friendly-Tool-Using-Streamlit-and-Plotly
ML_Phonepe Pulse Data Visualization and Exploration: A User-Friendly Tool Using Streamlit and Plotly
Here's the complete code with explanations for each section:

```python
# Importing necessary libraries
import plotly.express as px
from PIL import Image
import pandas as pd
import json
import os
import mysql.connector
import sqlite3
import streamlit as st

# Connecting to the SQLite database
conn = sqlite3.connect(r"C:\madhan\git\Pulse.db")
mycursor = conn.cursor()

# Setting up the Streamlit page
logo = Image.open("C:\madhan\git\logo.png")
st.set_page_config(page_title="Phonepe Pulse", page_icon=logo, layout='wide')

# Creating the sidebar menu
Menu = ["Home", "Top Charts", "Explore Data"]
choice = st.sidebar.selectbox("Menu", Menu)

# Home Section
if choice == "Home":
    img1 = Image.open('C:\madhan\git\phonpe.jpg')
    st.image(img1)
    st.markdown('# :violet[Data Visualization and Exploration]')
    st.markdown("## :violet[A User-Friendly Tool Using Streamlit and Plotly]")
    col1, col2 = st.columns([2,2], gap='medium')

    with col1:
        st.write(" ")
        st.write(' ')
        st.markdown('### :green[Domain:] Fintech')
        st.markdown('### :green[Technologies Used:]  Github Cloning, Python, Pandas, sqlite3, Streamlit, and Plotly')
        st.markdown('### :green[Overview:]  In this streamlit web app you can visualize the phonepe pulse data and gain lot of insights on transactions, number of users, top 10 state, district, pincode and which brand has most number of users and so on. Bar charts, Pie charts and Geo map visualization are used to get some insights."')
    
    with col2:
        img2 = Image.open('C:\madhan\git\img2.png')
        st.image(img2)

# Top Charts Section
elif choice == "Top Charts":
    st.markdown("## :red[TopCharts]")
    Type = st.sidebar.selectbox('**Type**', ("Transcations", "Users"))
    column1, column2 = st.columns([2,1.5], gap='Large')
    
    with column1:
        year = st.selectbox('**Select Year**', ('2018','2019','2020','2021','2022'), key='in_tr_yr')
        Quarters = st.selectbox('**Select Quarter**', ('1','2','3','4'), key='in_tr_qtr')
    
    with column2:
        st.info("""
                #### From this menu we can get insights like :
                - Overall ranking on a particular Year and Quarter.
                - Top 10 State, District, Pincode based on Total number of transaction and Total amount spent on phonepe.
                - Top 10 State, District, Pincode based on Total phonepe users and their app opening frequency.
                - Top 10 mobile brands and its percentage based on the how many people use phonepe.
                """, icon="🔍"
                )

    # Transactions Analysis
    if Type == 'Transcations':
        # Code for transaction analysis (state, district, pincode)
        # ...

    # Users Analysis
    if Type == 'Users':
        # Code for users analysis (brands, district, pincode, state)
        # ...

# Explore Data Section
elif choice == "Explore Data":
    year = st.selectbox('**Select Year**', ('2018', '2019', '2020', '2021', '2022'), key='in_tr_yr')
    Quarters = st.selectbox('**Select Quarter**', ('1', '2', '3', '4'), key='in_tr_qtr')
    Type = st.sidebar.selectbox('**Type**', ("Transcations", "Users"))
    col1, col2 = st.columns(2)

    if Type == "Transcations":
        # Code for transaction data exploration
        # ...

    if Type == "Users":
        # Code for user data exploration
        # ...

# The actual code for each analysis section (transaction analysis, user analysis, etc.) 
# would be included here, following the structure outlined in the previous explanation.
```

This code provides the structure for the Streamlit application. Each section (Home, Top Charts, Explore Data) is conditionally rendered based on the user's selection in the sidebar.

Within each section, there are further conditions and user inputs that determine what data is fetched from the database and how it's visualized. The actual SQL queries, data processing, and Plotly chart creation would be included within these sections.

Remember to replace the placeholder comments (# ...) with the actual implementation code for each analysis section. This would include the SQL queries, data processing with pandas, and chart creation with Plotly Express.
