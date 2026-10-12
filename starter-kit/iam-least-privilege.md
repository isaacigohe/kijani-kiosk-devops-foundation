# KijaniKiosk IAM Least Privilege Policy

## Scope & Use Case
This IAM policy defines strict, least-privilege permissions for the **KijaniKiosk Application Server Role**. The application requires read and write access to a specific Amazon S3 bucket (`kijani-app-media-storage`) to store and retrieve user-uploaded images, with no permission to modify other buckets or access other AWS resources.

---

## IAM Policy JSON

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowListKijaniBucket",
      "Effect": "Allow",
      "Action": [
        "s3:ListBucket"
      ],
      "Resource": "arn:aws:s3:::kijani-app-media-storage"
    },
    {
      "Sid": "AllowReadWriteKijaniObjects",
      "Effect": "Allow",
      "Action": [
        "s3:GetObject",
        "s3:PutObject",
        "s3:DeleteObject"
      ],
      "Resource": "arn:aws:s3:::kijani-app-media-storage/*"
    }
  ]
}
```

---

## Security Rationale
- **Principle of Least Privilege:** Limits access strictly to the single bucket required (`kijani-app-media-storage`).
- **Restricted Wildcards:** Avoids using `"Action": "*"` or `"Resource": "*"`.
- **No IAM Management:** The application role cannot modify IAM users, roles, or policies, preventing privilege escalation.
