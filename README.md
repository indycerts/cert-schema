[![Build Status](https://travis-ci.org/blockchain-certificates/cert-schema.svg?branch=master)](https://travis-ci.org/blockchain-certificates/cert-schema)
[![PyPI version](https://badge.fury.io/py/cert-schema.svg)](https://badge.fury.io/py/cert-schema)

# cert-schema

Blockchain Certificate schemas extend those of [Open Badges](https://openbadgespec.org/). As with Open Badges, we've provided both a JSON-LD context and JSON schema. The purpose of the JSON-LD context is to map types to Internationalized Resource Identifiers (IRIs), providing semantic context for data. The JSON Schema is used for syntactic validation.

This python package allows verification of a Blockchain Certificate against the JSON
schemas as a convenience. This is not the same as verifying the contents of a certificate against what is stored
on the blockchain. See the [cert-verifier-js](https://github.com/blockchain-certificates/cert-verifier-js) project.

*   [Blockcerts JSON Schema](docs/schema-2.md)

## Example

The following is a Blockchain Certificate issued on the testnet Bitcoin network.

```json
{
  "@context": [
    "https://w3id.org/openbadges/v2",
    "https://w3id.org/blockcerts/v2"
  ],
  "id": "urn:uuid:bc9bdbb5-d734-4242-9edc-d1bc3f8f7a6e",
  "type": "Assertion",
  "issuedOn": "2017-06-23T10:58:32.613613+00:00",
  "badge": {
    "id": "urn:uuid:87237a8d-1fe2-4707-a716-e70f3db778c7",
    "image": "data:image/png;base64,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",
    "issuer": {
      "id": "https://www.blockcerts.org/samples/2.0-alpha/issuerTestnet.json",
      "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAW0AAAFtCAYAAADMATsiAAAAAXNSR0IArs4c6QAAAAlwSFlzAAAuIwAALiMBeKU/dgAAActpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IlhNUCBDb3JlIDUuNC4wIj4KICAgPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9yZy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICAgICAgPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIKICAgICAgICAgICAgeG1sbnM6dGlmZj0iaHR0cDovL25zLmFkb2JlLmNvbS90aWZmLzEuMC8iCiAgICAgICAgICAgIHhtbG5zOnhtcD0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wLyI+CiAgICAgICAgIDx0aWZmOk9yaWVudGF0aW9uPjE8L3RpZmY6T3JpZW50YXRpb24+CiAgICAgICAgIDx4bXA6Q3JlYXRvclRvb2w+QWRvYmUgSW1hZ2VSZWFkeTwveG1wOkNyZWF0b3JUb29sPgogICAgICA8L3JkZjpEZXNjcmlwdGlvbj4KICAgPC9yZGY6UkRGPgo8L3g6eG1wbWV0YT4KsiN+8QAAIVFJREFUeAHt3QWsHNXbx/FTwYpDcS8EDxCc4NBAiwZIcQ9QPHhIsCKBwh8pEAhaIGiQFncplOAUK+5uLVDc5z3PvsxmZ54zu3tvd+aec893knZ3zo48+zlzf3fv7Egf8/9D8t8jDwgggAACHgv09bg2SkMAAQQQyAkQ2jkQRhFAAAGfBQhtn3uH2hBAAIGcAKGdA2EUAQQQ8Fmgf1FxScJ3k0U2tCOAAAJVCPTp00ethk/aioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF8BQtvfvqEyBBBAQAkQ2oqEBgQQQMBfAULb376hMgQQQEAJENqKhAYEEEDAXwFC29++oTIEEEBACRDaioQGBBBAwF+B/v6WFn5ln3/+uTn11FOdb2T//fc3K620kvO1xsbJkyeb4447rrGp/vy0004zAwcOrI/zxJgvvvjCnHLKKYpir732MmussYZqpwGB0AQI7RJ7bIEFFjCffPKJue+++9RaJNDvuusu1Z5vuPzyy82ll16abzbbbrstga1UjJkyZYrTa4MNNiC0HV40hSfA7pGS++yss85yruHuu+82r7zyivO1tPG3334z//vf/9LRzKN8ymZAAIH4BAjtkvt8+eWXN8OHD3eu5cwzz3S2p4033XST+e6779LR+uO+++5rlllmmfo4TxBAIB4BQruCvj7xxBNN//56T9SNN95o3n33XWcF//77rznjjDPUa3379jWyPAYEEIhTgNCuoN/nn39+c9JJJznXdPbZZzvb7733XmegH3300WbBBRd0zkMjAgj0fgFCu6I+Puyww5xfHMoXjZ9++qmqwrXrZIYZZjAS2q2GP//800ycONE88cQT5uuvv241uZevf//997UjQbwszlFUWeZJkpgvv/zS/P333461Tl1TWTVPXVXM3UpA/83eag5e75bATDPNZORLyb333jszv/xQjho1ypxzzjn19meffdY8+eST9fH0yYgRI8ycc86ZjmYeH374YXPdddeZCRMmmNdeey3z2myzzWZWX3312tETRx11lJllllkyr+dHTj/9dPUl6XbbbWe23377/KS18c8++8wceeSR6jWpZ5pppsm0X3zxxebxxx/PtMn7kn30cnij7BKSX2Q//vijWXfddWu/eDITezTSSfPGtzVp0iRz2WWXGdkOxo0bV7Po06ePWXHFFc1uu+1mDj300NrutuOPP179NSbb2CKLLNK4uMzzsmrOrISRSgQSu5bMPxsmDB0W+Ouvv5Jll1024yzu/fr1S7755pv62oYNG6ammWuuuZKff/65Pk36RJZpf3jV9Pn+TMcHDRqUvPTSS+nszsehQ4eq5Z188snOaaXx9ddfV9PL+uzRL2oe+0tLTTt+/PjE7ttP5phjjsxrNrTV/K0a3njjjcwy0vdtvz9oNWvbr5dhnq78zTffTGzoOt9D+l5WW2215IcffkjsL2I13auvvpouKvNYZs2ZFTHSUYG0zxsf2T1iNaoa5MvIc889V63un3/+MRdddFGtXb6YvOWWW9Q08gl0xhlnzLTLn80bbrih6crhfx988IFZeeWVzRVXXJFZVk+O/PLLL2azzTZzHinTk3W51l2muXyqlr75+OOPXauutz3//PNGjiCy6VBva/akzJqbrZfXyhVQv7E7+uuChWUENtlkE+Vt91fXPj0dfPDB6rUlllgikU9K+cH1idxuJmr+oraiT9xVf9JeddVVnTX7+Em7LPNff/01kb+mivqq3XbXJ+2yas5vj4x3XsDV73zStipVD64TbuREGrsLwsg+3/wgX0rmDxl8+umnnZ/I7Q9+bd+2/TPbfPvtt+bRRx81e+yxR36RtfFjjjnG2V514wsvvFD1Kru1vjLNr7nmmlp/5QubdtppjQ3d2j5u+Stt8803z0/SdLzMmpuumBdLF1C/4Tv/O4MlNgrss88+ytz2smqT/Zf2mO3GWWvja6+9tpp26aWXTuzp8Zlp05GRI0eq6WV9999/fzpJ/bHqT9rp+954442Tq6++OrFfpib2pKLE/tKp19Tuk7L2aUsflGX++++/J/PNN5/qHxvYyTvvvKPeut21paZNDRs/aZdZsyqKhlIE0n7NPdpRR1iUUgELrQvYw/xqX0C67Bvb7Cfl+jzpkxdffNH5QztmzJh0EvVoDxlLFl98cTWf/eSmpu2J0LZHpyR//PGHqqWrDWWFdpnmDzzwgOoX2QZuvfXWwre/0047OedpDO0yay4sjBc6KtCYBelzdo9YiZ4Y5ASZE044oemqhwwZUvuiMT/R22+/nW8ycgLPVlttpdrTBnuEijniiCPS0fqj3a9df95TT2TXz7XXXmtkV4CvQ5nmH374oXrbcqikXBSsaGjneP0yay6qi/byBQjt8o0L1yAhag9zK3zddRq7TPzWW2+peeQyrxLMzQZ7uKF6WS5lag8lVO1VNmyxxRZGThzyeSjT/P3331dvXY4ikWOziwZXX+anLbPm/LoYr06A0K7OWq1p5plnNq4zH2XCXXfdtfB623YXgFrWoosuqtryDXKpWNfgCg3XdGW1hXBafpnm7733nqJdYYUVVFtjw3TTTWfkS+dmQ5k1N1svr5UrQGiX69ty6XKctWuwX8q5mmttcrZgfhgwYEC+SY0XfZr96aef1LRVNjT7a6PKOpqtq0xzl3+rs1al1vzZpvn6y6w5vy7GqxMgtKuz7tia7FEiallys4VWg+wKcQ32LElXc9ttrsvHtj2znbDVbp2uLKusacs0t8fhq7Jffvll1dbYYI/bb3ltljJrbqyF59UKENrVendkbUsttZRajpzp2GpwXZhKvvyzh5tlZpU/vfODXFyoaJBjwnv7UKa5PapH8T311FNNz3j86KOP1Dz5hjJrzq+L8eoECO3qrDu2piWXXFItS05QcR0t0DihXL87P8gXmPkvvFwXpZITdYoG177TomlDbS/T3BXacrLVI488Ush14YUXFr6WvlBmzek6eKxegNCu3nyq12hP+zaufdj2BJrCZcuV/2677Tb1+pZbbqnaXPuYH3zwQeflQeUTn5zN19uHMs3tCVTqF6d4ypmQcgXF/PDQQw+ZdkK7zJrzNTFevYA6UL+jR4izsEIBe+SAsrfdn1x11VWF88gL5513nnO+/fbbL5Ez7BoHe13txH6xpaafffbZE/tlVeOktedXXnmlmlZq2nPPPevT290lib1wUSJnYcprrn/tXuWv2RUEVXEtGuynfmctcmLROuus06V/9iJembWVaW4vbeusW86UtNdiT+xNoGsn2xxwwAHO6VL/xpNrpPgya87gMFKKQNqvuUc76vihK6UCFqoEuhvaEogLLbSQ8wfYnqySrLfeeolcKGjhhRd2TiN9bu/y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qxZVXIuGrob2l19+qUzE0O5qarEmXkagHAFXNrN7xKr0huGee+5Rb0PO9rOfflV7//79a7sBVllllcxrjz32WG3f9iyzzJJpd41st912tWt2TDvttOrlqmtRBfzXcPjhh5tvvvkm8/KSSy6ZGW8ckSNrXIMNc9NsPtc8tCFQlgChXZZsxct955131BrlKoJFwworrGAkvP/+++/MJM8995yRfbvNBplPzhp0BbbMV2UtzeosOgSxaB55X/ILK/+lrIQ2AwK+CBDaPdgTckW59dZbr2UFjz/+uNlpp52aTidfJuaHUaNGmSuuuCLfXB//999/68/TJ5988kn6tPBRjv2WY72LhiprKaqhu+0LLbSQydf/2WefdXdxzIdAxwUI7Y6Ttr9A+XN8vvnmazmDnLjSbLDHEhtX2LZ71EnjsuXMxlbDggsuWDhJ1bUUFtLNF+aff34V2p9//nk3l8ZsCHRegOO0O29a+RLbCdp2i8rvLnHN1+yXSNW1uOqbmraZZppJzV60G0hNSAMCFQjwSbsC5LJXMc8885h+/fqZf/75J7Oqgw46qOlujMzE/43kv5x0TSPrKhqqrqWoju62y8k4+UF2mTAg4IsAoe1LT0xFHX379jXyxaLcIadxkOuLtBPCjfNM7XOfaunOe/nqq6/UbM12B6mJaUCgZAF2j5QMXNXil19+ebWqfIirCUpq8KmWrr5FV2gvsMACXV0M0yNQmgCftEujrXbBSy+9tFqh3AxYjjqZccYZ1Wsvv/yycR0SePPNN5t5551XTd+VBl9quf/++01+H/vCCy9s1l57befbkf35P/30k3qN0FYkNHggoM4EK+f8njiXWnRGZCev8idX3bP7mlU/ylX87AkmGXh7d3jnVQBt2GamkxHXGZEnn3yymq6xoaxaGtfRzvOunhFpP2UrP7kMgA3zdlbHNAh0XMD+blDbJLtHPPiN2YkSllhiCXPBBReoRclFqeR62muttZY55phjate8XmyxxZxXATzzzDPV/N1p8KmWrtTvuumB3K292RevXVk+0yLQCQF2j3RC0ZNl7L///mbMmDHmkUceURU988wzRv4VDXJ1wK222qro5S63+1RLu8Xb67SoSe1fKqqNBgR6UoBP2j2p3+F1y5Eb119/feEdZFyrk3kuueQS56d01/TttvlUS7s15+/kI98FyP0jGRDwSYDQ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",
      "email": "contact@issuer.org",
      "url": "https://www.blockcerts.org",
      "type": "Profile",
      "revocationList": "https://www.blockcerts.org/samples/2.0-alpha/revocationList.json",
      "name": "Issuer Institution Name"
    },
    "type": "BadgeClass",
    "signatureLines": [
      {
        "jobTitle": "CEO",
        "type": [
          "SignatureLine",
          "Extension"
        ],
        "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAJcAAABVBAMAAAC2kWv1AAAAMFBMVEX///8AAAC/v79/f39fX1+fn5/f398/Pz8fHx/Dw8NTU1Onp6cvLy93d3cnJydvb28isqiqAAAACXBIWXMAAA7EAAAOxAGVKw4bAAADQElEQVRYhe2WS27bMBCGp5RIudsCRbasX8iqUJ3Y3hIO7HZJSJayKAqw8StLIYnTLpNFnCv0BL1NT9MLdEhJzkNSEkfaFNAPmKQl6tNwNDMkQK1atV4nyqtjsbPqWODwCmF+hSyIKmTZvELYvEIWXFbIIgJgaUZMlobZwfAiphwHZVnz6/NuPCJRqyyMvE8G7HQpCC8HY1dJvx5Pg7AcCyy5AgihvyDrbkkUqAb0gbwjG26rkijyY9NiETSuaADOawD3Az5siEtLwoFrS5i9BnYRdwxWiqr9ZdQA0ubfOcKY2hFFJI8HCzYEDw6p24aFA4f4JSA3Zslhv5A1lEL3S3BPOkxQz1EjkDZs8JqfZxgb62+dKxYCucK+9ZOFXDiqKxzYULCnoujtU3xDgTc7uBoXf/zYXjB3yrhowWYAbwuDVc+GVcYms0hM6AYH5sL5SlpqfeLJHgwVtHpFsAPdtHVD77HWutVR8UvfpP1P3IE93lFYsjlWjgIW0YbFe4RpkmQx99CZXR/ob5Cjc0SO0BsRMF5cueNANtXTbBRJspirF+i0Hnx1KUQc+lgRW0RgSOBDKh9mls80hwpy+zlMksXowxEHYa1CCREL/jQ5tagEd2tBVkI3li6dTXk9sFtJshjRPfzOkzc3wG48OAM3pDa3tFFFJda4rIE/0lFH4KTJYjTf1y1RzMdZRxBw6iwHW4cUwbTrmzbWvVmaLGbxkzieiGchff/bANjHvypdSJ6autnorcbC1YltsuhnvHixIejaRTS5oYzFBSzQZZy6Oti9UzwrZZMFWXcOjz/jg/uPhVMw2Mc+monJwh4ki37RnSkmwCz1FKxtVjueoJXDRxOpcfj26xn04CkWTPRZkK572R2CjZIJ6f/oOcMwJAcw+6JY9s5BMmF7wU9sLRRzfWgP8qrQnJuOiLu5z+6VvmrLPE/QBGLxZwAPNJO6aGWULHK3XY1Nct1qpfydDijaXZ3s5Wk6mGTvFcuFvFWy6PHgRZK5hm0r4G7+X7JOzvxVZvAyNVXOxW0OjXaD5SqFEVEBLE2JSs79VtLvFBhFSqKl9Akx1kxjWCWGoQIOpPC0tbM6gVcZq1atWrVq1fqP9Q9Wkn4v31JdhQAAAABJRU5ErkJggg==",
        "name": "Big Boss"
      }
    ],
    "name": "This is the certificate title",
    "criteria": {
      "narrative": "Recipient must do work that makes them worthy of this badge"
    },
    "description": "This is the display description of the certificate."
  },
  "recipient": {
    "type": "email",
    "identity": "aryaxyz@starkxyz.com",
    "hashed": false
  },
  "recipientProfile": {
    "type": [
      "RecipientProfile",
      "Extension"
    ],
    "publicKey": "ecdsa-koblitz-pubkey:mtr98kany9G1XYNU74pRnfBQmaCg2FZLmc",
    "name": "Arya Stark"
  },
  "verification": {
    "type": [
      "MerkleProofVerification2017",
      "Extension"
    ],
    "publicKey": "ecdsa-koblitz-pubkey:msBCHdwaQ7N2ypBYupkp6uNxtr9Pg76imj"
  },
  "signature": {
    "type": [
      "MerkleProof2017",
      "Extension"
    ],
    "proof": [
      {
        "right": "62a1e26974f20cd38f1349a2c0975c98e3b7dbb821b7568f6790aae10c20032d"
      }
    ],
    "targetHash": "7d5ee19584a27a9bf7d558e0128a27e18f8d11ace3c99cd72423c9db6cbc50d7",
    "merkleRoot": "7570ad1a939b1d733668125df3e71ebbd593358e7d851eff3fdebd487462daab",
    "anchors": [
      {
        "type": "BTCOpReturn",
        "sourceId": "3608e5e893a4edb8634e79b43ceae4bd30153b80a7e91e3b9d65b1bd16485433"
      }
    ]
  }
}

```


## Running the python code locally

1. Ensure you have an python environment. [Recommendations](https://github.com/blockchain-certificates/cert-issuer/blob/master/docs/virtualenv.md)

2. Git clone the repository and change to the directory

  ```bash
  git clone https://github.com/blockchain-certificates/cert-schema.git && cd cert-schema
  ```

3. Run cert-schema setup

  ```bash
  pip install .
  ```


## Publishing package to pypi

- [First time info](http://peterdowns.com/posts/first-time-with-pypi.html)
- Publish script: `./release_package.sh`


## Unit tests

This project uses tox to validate against several python environments.

1. Ensure you have an python environment. [Recommendations](https://github.com/blockchain-certificates/developer-common-docs/blob/master/virtualenv.md)

2. Run tests
    ```
    ./run_tests.sh
    ```


## Compile markdown from schema

Note that json-schema-to-markdown doesn't handle ref schemas well, so you will 
need to manually update any 'undefined' references.

`scripts/generate_markdown.js` builds the markdown-formatted schemas from json

## Contact

Contact [info@blockcerts.org](mailto:info@blockcerts.org) with questions

