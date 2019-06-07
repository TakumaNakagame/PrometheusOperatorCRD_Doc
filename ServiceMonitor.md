# ServiceMonitor

## About
`ServiceMonitor`は、`matchLabels`などにマッチしたEndpointを監視します。

## Example

```
apiVersion: monitoring.coreos.com/v1
kind: ServiceMonitor
metadata:
  name: grafana
  namespace: monitoring
spec:
  endpoints:
  - interval: 15s
    port: http
  selector:
    matchLabels:
      app: grafana
```

## Config
`*`がついているのものは必須です。

### 全体像

- apiVersion
- kind
- metadata
  - name
- spec
  - endpoints*
    - basicAuth
      - password
      - username
        - key*
        - name
        - optinal
    - bearerTokenFile
    - honorLabels
    - interval
    - metricRelabelings
    - params
    - path
    - port
    - proxyUrl
    - metricRelabelings
      - action
      - modules
      - regex
      - replacement
      - separator
      - sourceLabels
      - targetLabel
    - scheme
    - scrapeTimeout
    - targetPort
    - tlsConfig
      - caFile
      - certFile
      - insecureSkipVerify
      - keyFile
      - serverName
  - jobLabel
  - namespaceSelector
    - any
    - matchNames
  - podTargetLabels
  - sampleLimit
  - selector*
    - matchExpressions
      - key*
      - operator*
      - values
    - matchLabels
  - targetLabels