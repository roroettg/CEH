`snmpwalk` is a command-line utility used to retrieve a subtree of management values from a network device using the Simple Network Management Protocol (SNMP). It is commonly used for network management and monitoring purposes. `snmpwalk` queries a network device for a series of Object Identifiers (OIDs) and returns the values associated with those OIDs.

### Examples of Using `snmpwalk`

1. **Basic Usage**:
   To perform a basic `snmpwalk` on a device with the IP address `192.168.1.1` using the community string `public`:
   ```bash
   snmpwalk -v 2c -c public 192.168.1.1
   ```

2. **Specifying an OID**:
   To retrieve information starting from a specific OID, for example, the system OID:
   ```bash
   snmpwalk -v 2c -c public 192.168.1.1 1.3.6.1.2.1.1
   ```

3. **Using SNMPv3**:
   For SNMPv3, which includes authentication and encryption, you need to provide additional parameters:
   ```bash
   snmpwalk -v 3 -u username -l authPriv -a MD5 -A authpass -x DES -X privpass 192.168.1.1
   ```

4. **Saving Output to a File**:
   To save the output of `snmpwalk` to a file for later analysis:
   ```bash
   snmpwalk -v 2c -c public 192.168.1.1 > snmpwalk_output.txt
   ```

5. **Filtering Results**:
   To filter the results for a specific keyword, you can use `grep`:
   ```bash
   snmpwalk -v 2c -c public 192.168.1.1 | grep ifDescr
   ```

These examples demonstrate how to use `snmpwalk` to query network devices for SNMP data, which can be useful for network administrators to monitor and manage network infrastructure.
