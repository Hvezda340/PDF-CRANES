<!DOCTYPE html>
<html>
<head>
    <title>Otevřít PDF</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
    <h1>Otevřít PDF soubor</h1>
    <input type="file" id="pdfUpload" accept="application/pdf">
    <iframe id="pdfViewer" style="width: 100%; height: 500px;"></iframe>

    <script>
        document.getElementById('pdfUpload').addEventListener('change', function(event) {
            const file = event.target.files[0];
            if (file && file.type === 'application/pdf') {
                const fileURL = URL.createObjectURL(file);
                document.getElementById('pdfViewer').src = fileURL;
            } else {
                alert('Vyberte platný PDF soubor.');
            }
        });
    </script>
</body>
</html>
