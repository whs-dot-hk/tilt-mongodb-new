def create_namespace(name):
    k8s_yaml(blob("""apiVersion: v1
kind: Namespace
metadata:
  name: %s
""" % name))

name = "mongodb-test"

create_namespace(name)

k8s_yaml(helm("charts/psmdb-operator", name = "%s-operator" % name, namespace = name))

k8s_yaml(helm("charts/psmdb-db", name = "%s-db" % name, namespace = name, values = "db.values.yaml"), allow_duplicates = True)

k8s_yaml(helm("charts/prometheus-mongodb-exporter", name = "%s-exporter" % name, namespace = name, values = "exporter.values.yaml"))
