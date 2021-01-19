# TRAGALDABAS-documentation
 This is the documentation of TRAGALDABAS

# ICRC Steps

## 1.- DAG [2 days]

- Produce "GoodActiveCells.root"
- Efficiency
- Time, charge calibration
- Data Quality => Select possible good ranges (For example, ranges A, B C)

## 2.- DAG & MYA & MCF [2 hours]

Check Grafana (HV, I, T, P, H) for each range [A, B, C] and select the best. For example, range A = [init date, final date].

## 3.- MCF [some hours]

Run unpack.sh code:
```bash
#!/bin/bash
for i in {306..335}
do
for a in `find /media/Datos2TB/tragaldabas/data/done/alberto/T01T02T03/20150107/done/ -type f -name tr20$i* -print`; do ./dst_nov2020.sh `basename $a`; done
done
```
and take files tryydoyhhmmss.hld.root.root

## 4.- MYA $ MCF [some days / week]

- Find event topology
    + With Python/PyROOT, take hits per event
        * hits T1
        * hits T3
        * hits T4
    + Separate by myltuplicity:
        * M1 (1, 1, 1) [~90%]
        * M2 (2, 2, 2) [~9%]
        * M3 (3, 3, 3) [~0.9%]
        * High Multiplicity (trash) [~0.09%]
- Yanis PID (Particle IDentification)
