
## CDN for source code
https://raw.githack.com/


# User Flow
## Issuer: receive a credential
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


## Verifier: proof a credential

not working atm: form at verifier-demo.polygonid.me does not support string input

1. Go to https://verifier-demo.polygonid.me/
2. Select `Custom`
3. Fill in Form for Query
    1. select `Circuit Id`: `Credential Atomic Query Signature`
    2. add `Url`: https://raw.githack.com/yvesbou/create-custom-polygonID-schema/master/credential-schema/proof-of-swissDAO-membership.json
    3. add `Type`: `ProofOfswissDAOMembership`
    4. add `Issuer`: `*`
    5. add `Field`: `partOfswissDAOLabs`
    6. add `Operator`: `EQ`
    7. add `Value`: `true`
    8. add `RequestID`: `1`
    5. submit
    6. scan QR code to receive send claim to your wallet


### Allowed Issuers
Note: 3.iv asterisk (*) means all Issuer are allowed
Part of the documentation says the following

> As part of the Query, the Verifier includes the identifiers of the trusted issuers. For example, a Verifier should add XYZ DAO as the only trusted Issuer when verifying that an individual is a member of XYZ DAO. XYZ DAO doesn’t need to accept nor interact with the Verifier.