import qrcode

# Data to encode in the QR code
data = "https://www.example.com"

# Create a QR code instance
qr = qrcode.QRCode(
    version=1,  # Version 1 means a 21x21 grid
    error_correction=qrcode.constants.ERROR_CORRECT_L,  # Error correction level
    box_size=10,  # Size of each box in the QR code
    border=4,  # Width of the border
)

# Add data to the QR code
qr.add_data(data)
qr.make(fit=True)

# Create an image from the QR code
img = qr.make_image(fill='black', back_color='white')

# Save the image
img.save("qrcode_example.png")

# Display the image (optional)
img.show()
