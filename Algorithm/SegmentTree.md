## 1. Segment Tree 란?

- 데이터 집합이 주어지고, 특정 구간의 합, 최대, 최소 값을 구해야하는 문제가 주어짐
- 이 때, 구간이 여러개이거나 데이터가 업데이트 될 수 있는 상황에서 더 빠르게 찾아내기 위해 고안된 자료구조

## 2. Sement Tree 사용 예제

- 입력으로 5, 2, 4, 3, 1이 들어왔다고 가정 + 업데이트를 반영한 구간합을 출력해야 되는 상황

## 2.1. 트리 초기화

- 입력으로 들어온 5개의 데이터를 모두 리프 노드에 넣어야 됨
  - 리프노드 : 자식이 없는 노드

<img width="500" alt="7" src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FwP1VS%2FbtrEkp9r4Bl%2FVloKNkMhgKkCBKv34nhVG1%2Fimg.png">

- 이런 식의 트리로 만드는게 목표
- 배열 사용 (루트 노드가 1번, 1번의 자식들이 순서대로 2, 3번, .... index가 8인 위치에 5를 넣어줌, .....)
- arr[1~15] = [0, 0, 0, 0, 0, 0, 0, 5, 2, 4, 3, 1, 0, 0, 0]
- 각각의 부모 노드들에 값을 채워넣음 => arr[ i ] = arr[ i * 2 ] + arr[ i * 2 + 1]
- arr[1~15] = [15, 14, 1, 7, 7, 1, 0, 5, 2, 4, 3, 1, 0, 0, 0]

<img width="500" alt="7" src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FpkjUJ%2FbtrEntiLt6R%2Fz6jvegQz4l0L61Tsy7legk%2Fimg.png">

## 2.2. 데이터 업데이트

- 3번째 값인 4를 7로 바꿔야 하는 상황
- 3번째 값의 처음 index = 10 => arr[10]을 4에서 7로 바꾸고 둘의 차이인 +3을 저장
- 부모노드들을 따라가면서 둘의 차이인 +3만큼 더해줌
  - index를 2로 나눠주면서 1까지 가면 됨
- arr[1~15] = [18, 17, 1, 7, 10, 1, 0, 5, 2, 7, 3, 1, 0, 0, 0]

<img width="500" alt="7" src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcE3bEF%2FbtrEnQYPoG3%2FCZ2enTQNc0xgi32sGgEXJ0%2Fimg.png">

## 2.3. 구간합 계산

- 2번째 값부터 4번째 값의 합을 구해야 함
- start = 9, end = 11
- start % 2 == 1 (오른쪽 노드)이면 해당 노드 값을 더해줌
- end % 2 == 0 (왼쪽 노드)이면 해당 노드 값을 더해줌
  - start가 오른쪽 노드이면 자기 자신만 더해줘야 하고, 왼쪽 노드이면 오른쪽 노드도 같이 더해야 되기 때문에 부모 노드를 더해야 하기 때문에 이 단계에서는 자기 자신을 더해주지 않음, end는 반대
- start = (start + 1) / 2, end = (end - 1) / 2
  - start가 왼쪽노드라면 자기 자신이 아닌 부모 노드값을 더해야 되고, 오른쪽 노드라면 자기 자신값에 부모의 오른쪽 값을 더해줘야 함, end는 반대
- 이 작업을 start > end 가 될 때 까지 반복
  - start == end인 경우에는 어느 한 쪽에서만 더해주게 됨
- sum = 2(9번 index) + 10(5번 index) = 12
- 만약 구간 최대/최소값 구하는 문제였다면 업데이트 할 때, 자식 중 큰/작은 값을 부모에 넣어주는 작업을 해주고 출력 할 때는 구간핪 계산과 똑같이 따라 올라가면서 가장 큰/작은 값 구하면 됨

## 3. 구현

https://www.acmicpc.net/problem/2042

2042번: 구간 합 구하기

- 이 문제를 Segment Tree를 통해 해결하면서 구현해봄

## 4. 코드

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.StringTokenizer;

public class Main {
    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        StringTokenizer st = new StringTokenizer(br.readLine());

        int n = Integer.parseInt(st.nextToken());
        int m = Integer.parseInt(st.nextToken()) + Integer.parseInt(st.nextToken());

        int depth = 0;
        while(Math.pow(2, depth) < n) {
            depth ++;
        }
        depth ++;
        int arraySize = (int)Math.pow(2, depth);
        int startIndex = (int)Math.pow(2, depth - 1);
        long[] tree = new long[arraySize];

        // 입력값들 트리에 넣기
        for(int i = 0 ; i < n ; i ++) {
            st = new StringTokenizer(br.readLine());
            long in = Long.parseLong(st.nextToken());
            tree[startIndex + i] = in;
        }

        // 초기 트리에 자식들의 합 채우기
        for(int i = startIndex - 1 ; i >= 1 ; i --) {
            tree[i] = tree[i * 2] + tree[i * 2 + 1];
        }

        for(int i = 0 ; i < m ; i ++) {
            st = new StringTokenizer(br.readLine());
            int op = Integer.parseInt(st.nextToken());
            long x = Long.parseLong(st.nextToken());
            long y = Long.parseLong(st.nextToken());

            // x번째 수를 y로 변경
            if(op == 1) {
                int targetIndex = (int) (startIndex + x - 1);
                long diff = y - tree[targetIndex];
                while(targetIndex > 0) {
                    tree[targetIndex] += diff;
                    targetIndex /= 2;
                }
            }
            // x부터 y까지의 합
            else {
                int s = (int)x + startIndex - 1;
                int e = (int)y + startIndex - 1;
                long ans = 0;
                while(s <= e) {
                    if(s % 2 == 1) ans += tree[s];
                    if(e % 2 == 0) ans += tree[e];
                    s = (s + 1) / 2;
                    e = (e - 1) / 2;
                }
                System.out.println(ans);
            }
        }
    }
}
```
