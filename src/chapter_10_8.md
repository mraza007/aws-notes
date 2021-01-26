# Amazon S3 Encryption

<table style="width:100%">
  <tr>
    <th>Option</th>
    <th>How it works</th>
  </tr>
  <tr>
  <td>SSE-S3</td>
  <td>Use S3's existing encryption key for AES-256</td> 
  </tr>
  <tr>
  <td>SSE-C</td>
  <td>Upload your own AES-256 encryption key which uses S3 uses when it writes objects</td>
  </tr>
  <tr>
  <td>SSE-KMS</td>
  <td>Use a key generated and managed by AWS KMS</td>
  </tr>
  <tr>
  <td>Client-Side</td>
  <td>Encrypt objects using your own local encryption process before uploading to S3</td>
  </tr>
</table>