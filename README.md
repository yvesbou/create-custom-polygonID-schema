
## CDN for source code
https://raw.githack.com/


## User Flow
1. Go to https://issuer-demo.polygonid.me
2. Connect PolygonID wallet (need mobile app)
3. Add claim
    1. select `Schema`: `Custom`
    2. add `Url`: https://raw.githack.com/yvesbou/create-custom-polygonID-schema/master/credential-schema/proof-of-swissDAO-membership.json
    3. add `Type`: `ProofOfswissDAOMembership`
    4. Data JSON: 
        ```JSON
        {
            "entryDate": 20230228,
            "partOfswissDAOLabs": true
        }
        ```
    5. submit
    6. scan QR code to receive send claim to your wallet
    7. inside app, you receive new claim `ProofOfswissDAOMembership`