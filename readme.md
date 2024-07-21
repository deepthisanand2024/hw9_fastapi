# RestAPI for Creating QR Codes

For this assignment the below fixes were made
1.	delete_qr_cde function was misspelt in qr_code.py. It is delete_qr_code
2.	app.include_router(qr_code.router) in main.py was spelt as 'ruter'
3.  Fixes in qr_code .py (@router.post("/qr-codes/", response_model=QRCodeResponse, status_code=status.HTTP_201_CREATED, tags=["QR Codes"])
4.  Instead of #status_code=status.HTTP_200_OK, replaced as status_code=status.HTTP_409_CONFLICT,
6.  @router.delete("/qr-codes/{qr_filename}", status_code=status.HTTP_204_NO_CONTENT, tags=["QR Codes"]). The ERROR code was status_code=status.HTTP_200_OK, 
7. Fixes in ouauth.py
    @router.post("/token", response_model=Token) was misspelt as tokn

8. Fixes to config.py : ADMIN_PASSWORD = os.getenv('ADMIN_PASSWORD', 'secret') was misspelt as “ecret”
9. Fixes to common.py:
    •	encode_url_to_filename function: sanitized_url attribute was misspelt
    •	decode_filename_to_url: base64.urlsafe_b64decode(encoded_str) was misspelt
10. Fixes to schema.py
    message: str = Field(..., description="A message related to the QR code request.")was misspelt as mssage
    