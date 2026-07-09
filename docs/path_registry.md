project:
  root_server: "/home/yourname/Smartnest"
  root_local: "C:/Users/yourname/Smartnest"

data:
  raw_images_server: "/data/smartnest/raw_images"
  experiments_server: "/data/smartnest/experiments"
  experiments_local: "D:/Smartnest/experiments"

models:
  fence_unet_best_server: "/data/smartnest/models/fence_unet_best.pth"
  fence_unet_best_local: "D:/Smartnest/models/fence_unet_best.pth"

outputs:
  masks_server: "/data/smartnest/outputs/masks"
  reports_server: "/data/smartnest/outputs/reports"
  logs_server: "/data/smartnest/outputs/logs"

remote:
  tailscale_server_name: "smartnest-server"
  tailscale_local_name: "your-local-pc"
