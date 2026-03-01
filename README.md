python - << 'EOF'
import ray
ray.init(address="auto")
print("Ray is alive")
print(ray.cluster_resources())
EO
