Triển khai Jenkins bằng Docker Container
1. Sử dụng Docker Image là `jenkins/jenkins:lts`
2. Chạy Docker Container ở chế độ ngầm (detach mode)
3. Tên của container là `jenkins-1`
4. Mở cổng 8080 của container ra cổng 8080 của máy host
5. Mở cổng 50000 của container ra cổng 50000 của máy host
6. Tạo volume để lưu trữ data của Jenkins

### Câu lệnh triển khai
```bash
docker run -d -p 8080:8080 -p 50000:50000 --name jenkins-1 -v jenkins-data:/var/jenkins_home jenkins/jenkins:lts
```

### Câu lệnh kiểm tra log của Jenkins
```bash
docker logs jenkins-1
```

### Câu lệnh lấy password của Jenkins
```bash
docker exec jenkins-1 cat /var/jenkins_home/secrets/initialAdminPassword
```

### Câu lệnh xóa container Jenkins
```bash
docker rm -f jenkins-1
```

### Câu lệnh xóa volume Jenkins
```bash
docker volume rm jenkins-data
```

### Câu lệnh xem thông tin volume Jenkins
```bash
docker volume inspect jenkins-data
```

### Câu lệnh xem thông tin container Jenkins
```bash
docker inspect jenkins-1
```

### Câu lệnh xem danh sách container đang chạy
```bash
docker ps
```

### Câu lệnh xem danh sách tất cả container
```bash
docker ps -a
```

### Câu lệnh xem danh sách image
```bash
docker images
```

### Câu lệnh xóa image
```bash
docker rmi <image_id>
```

### Câu lệnh xóa tất cả container đang tắt
```bash
docker container prune
```

### Câu lệnh xóa tất cả image không sử dụng
```bash
docker image prune
```

### Câu lệnh xóa tất cả volume không sử dụng
```bash
docker volume prune
```

### Câu lệnh xóa tất cả network không sử dụng
```bash
docker network prune
```