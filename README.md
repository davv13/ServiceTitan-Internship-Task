<body>
    <h1>Invoice Data Transformation</h1>
    <p>This project involves transforming unstructured invoice data into a structured format using a custom DataExtractor class. The data is loaded from a pickle file containing scanned invoices and a text file listing expired invoice IDs. Each invoice contains various properties and a list of items, which are also detailed with specific properties.</p>
    <p>The DataExtractor class performs the following tasks:</p>
    <ul>
        <li><strong>Initialization:</strong> Loads the invoices and expired invoice IDs.</li>
        <li><strong>Data Loading:</strong> Processes each invoice and its items to extract relevant information, calculate the total price and percentage of each item in the invoice, and check if the invoice is expired.</li>
        <li><strong>Data Transformation:</strong> Converts the loaded data into a structured pandas DataFrame with specified columns and data types.</li>
        <li><strong>Data Saving:</strong> Saves the transformed DataFrame to a CSV file.</li>
    </ul>
    <p>The resulting DataFrame includes the following columns:</p>
    <ul>
        <li>invoice_id: int</li>
        <li>created_on: datetime64[ns]</li>
        <li>invoiceitem_id: int</li>
        <li>invoiceitem_name: str</li>
        <li>type: str (converted from integer values using a predefined table)</li>
        <li>unit_price: int</li>
        <li>total_price: int (calculated as unit_price * quantity)</li>
        <li>percentage_in_invoice: float (calculated as total_price / invoice_total)</li>
        <li>is_expired: bool (indicating whether the invoice ID is in the expired invoices list)</li>
    </ul>
    <p>The DataFrame is sorted by invoice_id and invoiceitem_id in ascending order before being saved to a CSV file.</p>
</body>