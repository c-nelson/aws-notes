[RDS](RDS.md) Read Replicas can be added to an RDS Instance - 5 direct per primary instance.

They can be in the same region, or cross-region replicas.

Replication is asynchronous.

They provide read performance scaling for the instance, but also offer low RTO recovery for any instance failure issues.

Read only's can be promoted for fast recovery times.

Cannot help with data corruption because the corruption with be replicated.

![Pasted image 20250402204430.png](_atts/Pasted%20image%2020250402204430.png)