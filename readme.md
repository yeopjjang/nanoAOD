### Submit condor job ( Tested in KISTI GSDC server )  

### Grid Certificate  
 - Do voms-proxy  
```bash
voms-proxy-init

```  

 - Get a key of yout certificate  
```bash
voms-proxy-info
```  

 - You should copy and paste this key to following locations  
```bash
# job.jdl  
transfer_input_files = run_LNuLLA.sh, runStep1_LNuLLA.sh, runStep2_LNuLLA.sh, runStep3_LNuLLA.sh, runStep4_LNuLLA.sh,/cms/ldap_home/dylee/gridpack/test_slc6_amd64_gcc630_CMSSW_9_3_16_tarball.tar.xz,/tmp/x509up_u556951075  
```

```bash
# run_LNuLLA.sh
#!/bin/bash
TopDir=`pwd
export X509_USER_PROXY=${TopDir}/x509up_u556951075

```


