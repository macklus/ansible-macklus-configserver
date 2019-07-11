Ansible ConfigServer Role
=========================

ConfigServer products and free script role.

Role Variables
--------------

    macklus:
      configserver:
        cmm:
          install: true
        cmq:
          install: true
        cse:
          install: true
        csf:
          install: true
          options: {
            testing: 1,
            testing_interval: 5,
            auto_updates: 1,
            tcp_in: "20,21,22,25,53,80,110,143,443,465,587,993,995",
            tcp_out: "20,21,22,25,53,80,110,113,443,587,993,995",
            udp_in: "20,21,53",
            udp_out: "20,21,53,113,123"
          }
          allow: []      
          deny: []
          fignore: []
          ignore: []
          mignore: []
          pignore: []
          rignore: []
          signore: []
          suignore: []
        cxs:
          install: false
          install_cxswatch: false
          cxswatch:
            options: ''
            maxchild: 3
            loglevel: 0
            sleep: 3
            filemax: 0
            rateignore: 300
* **macklus.configserver.cmm.install:** Install CMM (true|false)
* **macklus.configserver.cmq.install:** Install CMQ (true|false)
* **macklus.configserver.cse.install:** Install CSE (true|false)
* **macklus.configserver.csf.install:** Install CSF (true|false)
* **macklus.configserver.csf.options:** Options that should be on csf.conf file (dict of lowercase variable - value)
* **macklus.configserver.csf.allow:** Config lines for csf.allow file (list of string lines)
* **macklus.configserver.csf.deny:** Config lines for csf.deny file (list of string lines)
* **macklus.configserver.csf.fignore:** Config lines for csf.fignore file (list of string lines)
* **macklus.configserver.csf.mignore:** Config lines for csf.mignore file (list of string lines)
* **macklus.configserver.csf.pignore:** Config lines for csf.pignore file (list of string lines)
* **macklus.configserver.csf.rignore:** Config lines for csf.rignore file (list of string lines)
* **macklus.configserver.csf.signore:** Config lines for csf.signore file (list of string lines)
* **macklus.configserver.csf.suignore:** Config lines for csf.suignore file (list of string lines)

For cxs:
* **macklus.configserver.cxs.install:** Install CXS

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
        - macklus.configserver/cmm
        - macklus.configserver/cmq
        - macklus.configserver/cse
        - macklus.configserver/csf
        - macklus.configserver/cxs

License
-------

GPL-3.0-only