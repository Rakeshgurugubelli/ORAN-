**On board step by step**

```
1. PNFD already exists in SMO (YAML/CSAR descriptor)
        ↓
2. RU (PNF) is installed and powered ON
        ↓
3. DHCP assigns IP + bootstrap info
        ↓
4. PNF contacts bootstrap / discovery endpoint
        ↓
5. PNF gets:
   - SMO / NETCONF endpoint
   - certificates
   - configuration details
        ↓
6. PNF sends registration event (JSON/YANG model)
   (serial number, vendor, location, capabilities)
        ↓
7. SMO validates:
   - matches PNFD
   - checks serial / vendor / location
        ↓
8. SMO changes status:
   - UNDISCOVERED → REGISTERED → ONBOARDED
        ↓
9. SMO configures PNF via O1 / NETCONF
        ↓
10. PNF becomes fully managed

```

Bootstrap info = 
the initial configuration details given to a newly powered network device so it knows where and how to connect for further setup and management.

