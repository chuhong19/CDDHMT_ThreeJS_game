# CDDHMT_ThreeJS_game

Các bước thực hiện trong quy trình tạo ra trò chơi
- Tạo scene
- Tạo ánh sáng
- Đặt camera
- Tạo xe (bánh xe, thân xe, cabin), tạo texture dán đầu xe và thân xe từ các hình chữ nhật với canvas
- Tạo 1 mặt phẳng lớn chứa toàn bộ mọi thứ, map trò chơi là texture trên mặt phẳng đó
- Tạo map 
- Tính toán các giá trị dựng map
- Tạo các phần của map (left, mid, right, field) theo giá trị
- Tạo dấu đường đi: getLineMarkings)
- Render map
- Xây dựng logic game
- Xử lí giao diện gồm bảng hướng dẫn, thông báo khi chơi lại

Camera sử dụng camera trực giao
Dùng 2 loại ánh sáng là ánh sáng trắng tự nhiên và ánh sáng trực tiếp
Xe được tạo dưới dạng 1 group của ThreeJS, màu random và 2 texture trước và bên thân xe tạo từ các hình chữ nhật trong canvas
Bánh xe cũng tạo hàm tạo riêng, với hình dạng là 1 hình chữ nhật 
Map được dựng bằng 4 phần, một phần hình tròn (arc) nằm bên trái, phần ở giữa, arc bên phải và outer field, được ghép bằng 2 arc lớn lại với nhau
Đo đạc các vị trí góc biên của arc, sau đó dựng cung tròn từ điểm bắt đầu và điểm cuối để tạo arc (context.arc)
Các vòng tròn inner và outer được tính bằng bán kính cộng trừ độ lệch là chiều rộng đường đua
Tạo dấu đường đi bằng hàm getLineMarking và lệnh stroke với lineWidth = 2 để tạo nét đứt
Logic game:
  + Nguyên tắc trò chơi: điều khiển 2 xe ô tô (bằng cách tăng và giảm tốc độ mỗi chiếc) trên map để không đụng nhau
  + Hàm reset để khởi động lại mọi thứ về ban đầu (khi va chạm), cũng như trạng thái bắt đầu trò chơi
  + Hàm movePlayerCar để xác định vị trí xe theo (thời gian, tốc độ) 
  + Hàm getPlayerSpeed xử lí tốc độ xe, tính theo phím nhấn tăng/ giảm tốc của người chơi
  + EventListener để nhận ấn phím từ bàn phím
  + Tính điều kiện va chạm khi khoảng cách 2 xe dưới ngưỡng cho phép
  + Hàm resolveHit để xử lí khi va chạm, đặt lại biến reset

function pickRandom(array) 

function getDistance(coordinate1, coordinate2) 

// Initialize ThreeJs
// Set up camera

// Set up lights

// Set up renderer

function reset() 

function startGame() 

function getLineMarkingscircle()
	return new THREE.CanvasTexture(canvas);

function getCurbsTexture(mapWidth, mapHeight) 
	return new THREE.CanvasTexture(canvas);

function getLeftIsland()	
	return islandLeft;

function getMiddleIsland() 
	return islandMiddle;

function getRightIsland()
	return islandRight;

function getOuterField(mapWidth, mapHeight) 
	return field;

function renderMap(mapWidth, mapHeight) 	

function getCarFrontTexture() 
	return new THREE.CanvasTexture(canvas);

function getCarSideTexture() 
	return new THREE.CanvasTexture(canvas);

function Car() 
	const car = new THREE.Group();
	return car;

function Wheel() 

function Tree()

accelerateButton.addEventListener

function animation(timestamp) 

function movePlayerCar(timeDelta) 

function getPlayerSpeed() 
	return speed;

function getHitZonePosition(center, angle, clockwise, distance) 
  return {
    x: center.x + Math.cos(directionAngle) * distance,
    y: center.y + Math.sin(directionAngle) * distance
  }

function resolveHit() 

function hitDetection() 

window.addEventListener
