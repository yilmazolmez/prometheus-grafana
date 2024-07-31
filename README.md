# prometheus-grafana


## Prometheus ve Grafana Kurulumu

Bu projede, Prometheus ve Grafana'yı konteyner olarak çalıştırmak için aşağıdaki adımları izleyin.

### 1. Docker Ağını Oluşturma

Öncelikle, Prometheus ve Grafana'nın aynı ağda çalışabilmesi için bir Docker ağı oluşturun:

```bash
docker network create monitoring

docker run -d --name prometheus --network monitoring -p 9090:9090 prom/prometheus

docker run -d --name grafana --network monitoring -p 3000:3000 grafana/grafana

```

## Prometheus ile Grafana'yı Bağlama
Grafana'yı açtıktan sonra, Prometheus veri kaynağını ekleyerek Grafana ile bağlayın. 
Grafana'da Configuration > Data Sources kısmına gidin ve yeni bir veri kaynağı ekleyin.
 URL olarak http://prometheus:9090 kullanın.

## Servislere Erişim
Prometheus: http://localhost:9090
Grafana: http://localhost:3000

Prometheus'un prometheus.yml dosyasına gerekli scrape ayarlarını eklemeyi unutmayın.
