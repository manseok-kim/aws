
# AWS Storage gp3

## 성능
||gp3|gp2|   
|-|-|-|  
|IOPS| baseline iops 3,000(125 MiB/s)| 3 IOPS / GiB |
|Max IOPS per volume| 16,000 | 16,000|
|Max throughput per volume| 1,000 MiB/s| 250 MiB/s|

<br>

## 가격 정책
|Volume Type	| Price|
|-|-|
|gp3 Storage |	$0.0912/GB-month |
| gp3 – IOPS |	3,000 IOPS free and $0.0057/provisioned IOPS-month over 3,000 |
| gp3 – Throughput | 125 MB/s free and $0.0456/provisioned MB/s-month over 125 |
| gp2 Volumes |	$0.114 per GB-month of provisioned storage |

<br>

## 가격 비교
### 100GB  
- gp2 타입의 EBS
1.  가격 : $0.114 * 100GB = 월 $11.4
2. IOPS : 3 IOPS * 100GB = 300 IOPS
3. 처리량 : I/O당 256KB/s * 300 IOPS = 75 MB/s
- gp3 타입의 EBS
1. 가격 : $0.0912 * 100GB = 월 $9.2
2. IOPS : 3000 IOPS 고정
3. 처리량 : 125 MB/s

### 200GB
- gp2 타입의 EBS
1. 가격 : $0.114 * 200GB = 월 $22.8
2. IOPS : 3 IOPS * 200GB = 600 IOPS
3. 처리량 : 150 MB/s (부스트 시에 최대 250 MB/s)
- gp3 타입의 EBS + 25MB/s의 추가 처리량
1. 가격 : $0.0912 * 200GB + $0.0456 * 25 MB/s = 월 $19.54
2. IOPS : 3000 IOPS
3. 처리량 : 150 MB/s
**비고 : 처리량을 220MB/s로 끌어올려도 $22.732**
### 500GB
- gp2 타입의 EBS
1. 가격 : $0.114 * 500GB = 월 $57
2. IOPS : 3 IOPS * 500GB = 1500 IOPS
3. 처리량 : 250MB/s
- gp3 타입의 EBS + 125MB/s의 추가 처리량
1. 가격 : $0.0912 * 500GB + $0.0456 * 125 MB/s = 월 $51.7
2. IOPS : 3000 IOPS
3. 처리량 : 250 MB/s