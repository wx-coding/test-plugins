---
name: amap-maps-weather
description: 高德地图服务集成，提供地图搜索、路径规划、地理编码、天气查询等一体化地图服务功能
license: MIT
allowed-tools:
  - mcp__amap-service__maps_text_search
  - mcp__amap-service__maps_geo
  - mcp__amap-service__maps_regeocode
  - mcp__amap-service__maps_around_search
  - mcp__amap-service__maps_search_detail
  - mcp__amap-service__maps_direction_driving
  - mcp__amap-service__maps_direction_walking
  - mcp__amap-service__maps_direction_bicycling
  - mcp__amap-service__maps_direction_transit_integrated
  - mcp__amap-service__maps_distance
  - mcp__amap-service__maps_weather
  - mcp__amap-service__maps_ip_location
  - mcp__amap-service__maps_schema_navi
  - mcp__amap-service__maps_schema_take_taxi
  - mcp__amap-service__maps_schema_personal_map
metadata:
  version: "1.0.0"
  author: "Claude Code Assistant"
  tags: ["map", "weather", "location", "navigation", "poi"]
  category: "location-services"
---

# 高德地图天气服务 Skill

## 概述

本Skill集成了高德地图服务API，提供完整的地理位置、路径规划和天气查询功能。当用户需要进行地理位置相关的查询、导航规划或天气信息获取时使用此Skill。

## 核心功能

### 1. 地理信息查询
- **地理编码**：将详细地址转换为经纬度坐标
- **反地理编码**：将经纬度坐标转换为结构化地址信息
- **POI搜索**：根据关键词搜索兴趣点
- **周边搜索**：在指定位置周围搜索相关设施
- **POI详情**：获取兴趣点的详细信息

### 2. 路径规划
- **驾车导航**：为小客车、轿车规划最优驾驶路线
- **步行导航**：规划100km以内的步行路线
- **骑行导航**：规划自行车骑行路线（最大500km）
- **公共交通**：综合火车、公交、地铁的公共出行方案
- **距离测量**：计算两点间的驾车、步行或直线距离

### 3. 生活服务
- **天气查询**：根据城市名称查询实时天气信息
- **IP定位**：根据IP地址进行地理位置定位
- **打车服务**：生成高德地图打车URI链接
- **地图导航**：生成导航页面URI链接

### 4. 地图应用
- **个人地图**：创建个性化行程规划地图
- **URI生成**：生成可直接调用高德地图App的链接

## 使用指南

### 地理查询类任务
当用户需要：
- 查找具体位置的坐标
- 根据坐标获取地址信息
- 搜索特定类型的地点（餐厅、酒店、加油站等）
- 查找当前位置周边的服务设施

### 出行规划类任务
当用户需要：
- 规划从A地到B地的最优路线
- 比较不同出行方式的时间和距离
- 查询公共交通换乘方案
- 计算行程距离和预估时间

### 天气查询类任务
当用户需要：
- 查询指定城市的天气情况
- 获取出行目的地的天气信息
- 为行程规划提供天气参考

## 工作流程

1. **理解用户需求**：明确用户要查询的具体信息类型
2. **选择合适的API**：根据需求选择对应的地图服务API
3. **参数准备**：准备必要的参数（地址、坐标、关键词等）
4. **调用API服务**：使用MCP工具调用高德地图服务
5. **结果处理**：整理和呈现API返回的信息
6. **提供附加建议**：根据结果提供实用的后续建议

## 最佳实践

- 使用准确的地址信息和坐标
- 对于模糊查询，提供多个备选结果
- 在路径规划时考虑实时交通因素
- 天气查询时建议使用城市名称或adcode
- 生成地图链接时验证坐标和地址的准确性

## 错误处理

- 地址解析失败时，建议用户提供更详细的地址信息
- 路径规划失败时，建议检查起终点的有效性
- 天气查询失败时，确认城市名称的正确性
- 网络超时时，建议用户稍后重试

## 注意事项

- 所有API调用需要网络连接
- 坐标格式为：经度,纬度
- 距离单位默认为米
- 时间计算考虑实时交通状况
- 某些高级功能可能需要API权限