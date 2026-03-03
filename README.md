python3 - << 'EOF'
import ray
ray.init(address="10.148.63.41:6379")
print("Ray is alive:", ray.is_initialized())
print(ray.nodes())
EOF
