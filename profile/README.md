# XJDAO

[![Website](https://img.shields.io/badge/xjdao.xyz-1fb931?style=flat-square&logo=discourse&logoColor=white)](https://xjdao.xyz/)
[![AT Protocol](https://img.shields.io/badge/Built%20on-AT%20Protocol-blue?style=flat-square&logo=bluesky&logoColor=white)](https://atproto.com/)

XJDAO is a social network platform designed for rural builders and innovators. We bridge the digital and physical worlds to create new forms of community that connect cloud-based collaboration with ground-level rural development. Our mission is to build digital infrastructure that empowers young talent to participate meaningfully in rural revitalization.

## Overview

XJDAO is built on the [AT Protocol](https://atproto.com/) (the open protocol behind Bluesky), providing a decentralized foundation for social networking. The platform enables:

- **Decentralized Identity**: Using PLC (Placeholder) DID method for persistent, portable identities
- **Federated Architecture**: Distributed Personal Data Servers (PDS) for user data sovereignty
- **Rich Social Features**: Timeline feeds, social graphs, and content discovery
- **Custom App Views**: Tailored experiences for rural development communities

## Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                              XJDAO Architecture                             │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────┐      ┌─────────────────┐      ┌─────────────────────────┐
│   PLC Server    │────▶│  PDS (Personal  │────▶│   AppView (BSKY)        │
│  (DID Method)   │      │  Data Server)   │      │   - Timeline            │
│                 │      │                 │      │   - Social Graph        │
└─────────────────┘      └─────────────────┘      └─────────────────────────┘
                                                          │
                                                          ▼
                                               ┌─────────────────────────┐
                                               │     Post Cache          │
                                               │   (Content Indexing)    │
                                               └───────────┬─────────────┘
                                                           │
                                                           |
         ┌─────────────────────┐                           |
         │  Xiangjiandao Core  │                           |
         │   (Backend API)     │                           |
         │                     │                           |
         └──────────┬──────────┘                           |
                    │          ----------------------------
                    │ API      | API
                    ▼          ▼
    ┌─────────────────────────────┐         ┌─────────────────────────────┐
    │      Social App             │         │      Social App Admin       │
    │   (Web Frontend - Users)    │         │    (Admin Dashboard)        │
    │                             │         │                             │
    └─────────────────────────────┘         └─────────────────────────────┘
```


## Repositories

| Repository | Description | Docker Image | Helm Chart |
|------------|-------------|--------------|------------|
| [atproto](https://github.com/xjdao2025/atproto) | AT Protocol infrastructure (BSKY + PDS) | `bsky`, `pds` | - |
| [did-method-plc](https://github.com/xjdao2025/did-method-plc) | DID PLC server for decentralized identity | `did-method-plc` | - |
| [post_cache](https://github.com/xjdao2025/post_cache) | Application view and content caching layer | `post_cache` | - |
| [social-app](https://github.com/xjdao2025/social-app) | Main frontend application (users) | `social-app` | `charts/social-app` |
| [social-app-admin](https://github.com/xjdao2025/social-app-admin) | Admin dashboard frontend | `social-app-admin` | `charts/social-app-admin` |
| [xiangjiandao-core](https://github.com/xjdao2025/xiangjiandao-core) | Backend API and core services | `xiangjiandao-core` | `xiangjiandao` |
| [web5_deploy](https://github.com/xjdao2025/web5_deploy) | Infrastructure-as-code and deployment configs | N/A | N/A |

## Deployment

### AT Protocol Services

The core AT Protocol infrastructure (PLC, PDS, BSKY, post_cache) is deployed using k8s yamls in the [web5_deploy](https://github.com/xjdao2025/web5_deploy) repository.

### Application Services

The custom XJDAO services (social-app, social-app-admin, xiangjiandao-core) are deployed via Helm charts.


See individual repository READMEs for detailed deployment instructions.

## Technology Stack

- **Protocol**: AT Protocol
- **Identity**: DID PLC
- **Backend**: Node.js / Rust / C#
- **Frontend**: React
- **Infrastructure**: Docker, Kubernetes, Helm
- **Database**: PostgreSQL, Redis, RabbitMQ

## Contributing

We welcome contributions from developers passionate about rural development and decentralized social networking. Please see individual repository contribution guidelines.

## License

See individual repositories for license information.

## Acknowledgments

XJDAO is built upon the open-source [AT Protocol](https://atproto.com/) and is inspired by the [Bluesky](https://bsky.app/) project's vision for a decentralized social web.

---

**Connect with us**: [xjdao.xyz](https://xjdao.xyz/)
