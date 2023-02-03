import streamlit as st
import pandas as pd

# Data to store invoices
data = {"Invoice No": [], "Client": [], "Date": [], "Project": [], "Amount": [], "VAT": [], "Description": []}
df = pd.DataFrame(data)

# List of authorized clients
clients = ["Client A", "Client B", "Client C"]

def new_invoice_form(client):
    invoice_no = len(df) + 1
    date = st.date_input("Date")
    project = st.text_input("Project")
    amount = st.number_input("Amount")
    vat = st.number_input("VAT")
    description = st.text_area("Description")
    create = st.button("Create")
    if create:
        df_new = pd.DataFrame({"Invoice No": [invoice_no], "Client": [client], "Date": [date], "Project": [project], "Amount": [amount], "VAT": [vat], "Description": [description]})
        df = df.append(df_new)
        st.success("Invoice created successfully!")
        # print the invoice in word based on the template
        # Code to generate the invoice based on the template goes here

def main():
    client = st.selectbox("Select Client", clients)
    if client:
        new_invoice_form(client)
    st.write("Invoices Issued:", df)

if __name__ == "__main__":
    main()
