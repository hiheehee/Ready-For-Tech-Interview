# Cache
* 데이터나 값을 미리 복사해 놓는 임시 장소
* 원본 데이터를 접근하는 시간이 오래 걸리는 경우 사용
* 값을 다시 계산하는 시간을 절약하는 경우 사용
* 캐시에 데이터를 미리 복사해 놓으면 계산이나 접근 시간 없이 빠른 속도로 데이터에 접근 가능

# 페이지 교체 알고리즘의 종류
* OPT (Optimal) : 앞으로 가장 오랫동안 사용되지 않을 페이지 교체
* FIFO (First In First Out) : 가장 먼저 올라온 페이지 교체
* LRU (Least Recently Used) : 가장 오랫동안 사용되지 않은 페이지 교체
* LFU (Least Frequently Used): 참조 횟수가 가장 작은 페이지 교체
* MFU (Most Frequently Used) : 참조 횟수가 가장 많은 페이지 교체
* NUR (Not Used Recently) : 최근에 사용하지 않은 페이지 교체
