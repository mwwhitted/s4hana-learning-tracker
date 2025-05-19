# 📘 S/4HANA Developer Training Tracker (RAP Learning App)

This is a practice project built to develop and showcase SAP ABAP RESTful Application Programming Model (RAP) skills in an S/4HANA environment. The app helps track developer training modules, skills progress, and certification goals.

---

## 🎯 Project Goals

- Practice modern RAP development
- Implement CDS Views, Behavior Definitions, and Service Bindings
- Expose OData v4 services for UI/API consumption
- Integrate with CPI (optional)
- Build a Fiori Elements-ready training tracker UI

---

## 📐 Architecture Overview

- **Data Model**: Custom Z-tables (`ZCOURSE`, `ZSKILL`, `ZPROGRESS`)
- **CDS Views**: UI annotations, value help, virtual fields
- **RAP Logic**: Behavior Definitions and Implementations
- **OData v4**: Service Definition + Service Binding
- **Optional**: Draft handling, feedback logging, CPI integration

---

## 🧱 Database Tables

| Table        | Description                      |
|--------------|----------------------------------|
| `ZCOURSE`    | List of training courses         |
| `ZSKILL`     | Skills/topics covered            |
| `ZPROGRESS`  | User progress across courses     |
| `ZFEEDBACK`  | Optional feedback per course     |

---

## 🗂️ Key RAP Artifacts

| Type              | Object Name             | Description                        |
|-------------------|-------------------------|------------------------------------|
| CDS View          | `ZC_COURSE`, `ZI_COURSE`| Course entity interface/view       |
| Behavior Def      | `ZC_COURSE` BDEF        | Create/Update/Delete logic         |
| Service Definition| `ZSD_COURSE`            | Wraps exposed entities             |
| Service Binding   | `ZSB_COURSE` (OData V4) | Publishes the service              |

---

## 🔄 OData Test Scenarios

Use tools like **Postman** or **SAP Gateway Client**:

- `GET /sap/opu/odata4/sap/ZSB_COURSE/` – metadata
- `GET /.../ZC_COURSE?$expand=Skills` – entity relationships
- `POST /ZC_PROGRESS` – update progress from CPI

---

## 🛠 Setup Instructions

1. Clone the project using [abapGit](https://docs.abapgit.org/)
2. Import objects into your S/4HANA on-prem or cloud system
3. Activate RAP objects in proper order:
    - Tables → CDS Views → BDEF → Service Def/Bind
4. Test OData in SAP Gateway Client
5. (Optional) Connect to CPI for external updates

---

## 🧪 Development Roadmap

See the [📘 Notion Task Tracker](#) for full task breakdown.

| Phase | Focus                               |
|-------|-------------------------------------|
| 1     | RAP CRUD + CDS + OData              |
| 2     | Draft handling + computed fields    |
| 3     | Metadata validation + Fiori UI      |
| 4     | CPI integration + abapGit packaging |

---

## 📦 Author

Built by Mark Whitted as a learning project for S/4HANA ABAP RAP development.

---

## 📜 License

MIT License – Use freely, adapt, and extend.
