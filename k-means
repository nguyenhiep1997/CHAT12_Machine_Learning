import matplotlib.pyplot as plt
import random
from sklearn.cluster import KMeans

def generate_random_clusters(num_points=50, num_clusters=5, value_range=(0, 50), spread=4):
    points_per_cluster = num_points // num_clusters
    a, b = [], []

    # Sinh ngẫu nhiên các tâm cụm trong khoảng [0, 50]
    centers = [(random.randint(*value_range), random.randint(*value_range)) for _ in range(num_clusters)]

    for cx, cy in centers:
        for _ in range(points_per_cluster):
            ai = min(max(random.randint(cx - spread, cx + spread), value_range[0]), value_range[1])
            bi = min(max(random.randint(cy - spread, cy + spread), value_range[0]), value_range[1])
            a.append(ai)
            b.append(bi)

    return a, b, centers


# Ví dụ sử dụng
x, y, centers = generate_random_clusters()
print("x =", x)
print("y =", y)
print("centers =", centers)

# Example usage:
#x = [20, 8, 10, 4, 3, 11, 14 , 6, 10, 12]
#y = [21, 19, 24, 17, 16, 25, 24, 22, 21, 21]

#plt.scatter(x, y)
#plt.show()
# create
data = list(zip(x, y))
inertias = []
# khoi tao ban dau voi so cluster là 1 và tối đa là 11, check xem so luong bao nhieu cluster thi toi uu
#for i in range(1,11):
#    kmeans = KMeans(n_clusters=i)
#    kmeans.fit(data)
#    inertias.append(kmeans.inertia_)

#plt.plot(range(1,11), inertias, marker='o')
#plt.title('Elbow method')
#plt.xlabel('Number of clusters')
#plt.ylabel('Inertia')
#plt.show()

kmeans = KMeans(n_clusters=5)
kmeans.fit(data)

plt.scatter(x, y, c=kmeans.labels_)
plt.show()
