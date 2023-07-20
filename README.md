![header](https://capsule-render.vercel.app/api?type=rect&color=gradient&height=200&section=header&text=Jeongho's%20Github&fontSize=90&animation=fadeIn)
<br>
# Hi I'm Jeongho🙌
<a href="https://hits.seeyoufarm.com"><img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fcuzzzu1318%2Fhit-counter&count_bg=%232FBCB2&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false"/></a>
<br/><br/>
![Top Langs](https://github-readme-stats-ivory-three.vercel.app/api/top-langs/?username=cuzzzu1318&layout=demo&theme=dark) 
[![Jeongho's GitHub stats](https://github-readme-stats-ivory-three.vercel.app/api?username=cuzzzu1318)](https://github.com/cuzzzu1318/github-readme-stats)

<br/><br/>
## 💻Tech Stacks
<div>
<img src="https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=Java&logoColor=black">
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=black">
<img src="https://img.shields.io/badge/C-A8B9CC?style=for-the-badge&logo=C&logoColor=black">
<img src="https://img.shields.io/badge/Lua-2C2D72?style=for-the-badge&logo=Lua&logoColor=black">
<img src="https://img.shields.io/badge/MYSQL-4479A1?style=for-the-badge&logo=MySQL&logoColor=black">
<img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=black">
<img src="https://img.shields.io/badge/HTML-E34F26?style=for-the-badge&logo=HTML5&logoColor=black">
<img src="https://img.shields.io/badge/CSS-1572B6?style=for-the-badge&logo=CSS3&logoColor=black">
<img src="https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=PHP&logoColor=black">
    
</div>
<br/>

## ❓Solved.ac

[![Solved.ac](http://mazassumnida.wtf/api/v2/generate_badge?boj=cuzzzu1318)](https://solved.ac/cuzzzu1318)

```java
package jul_2023;

import java.io.BufferedReader;
import java.io.FileInputStream;
import java.io.InputStreamReader;
import java.util.ArrayList;
import java.util.Arrays;

public class S2_BOJ15663_0720 {
	static int N;
	static int M;
	static int[] nums;
	static ArrayList<String> arr = new ArrayList<>();
	static boolean[] v;
	static int[] ans;
	static StringBuilder sb = new StringBuilder();
	
	public static void main(String[] args) throws Exception {
		//System.setIn(new FileInputStream("C:\\Users\\JH\\git\\Algorithm\\Baekjoon\\src\\input.txt"));
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		String[] s = br.readLine().split(" ");
		N = Integer.parseInt(s[0]);
		M = Integer.parseInt(s[1]);
		nums = new int[N];
		
		s = br.readLine().split(" ");
		//숫자 입력
		for(int i = 0;i<N;i++) {
			nums[i] = Integer.parseInt(s[i]);
		}
		//사전순 정렬을 위해 숫자 배열 먼저 정렬
		Arrays.sort(nums);
		
		//답을 저장할 배열 및 방문배열 초기화
		ans = new int[M];
		v = new boolean[N];
		//dfs(백트래킹)
		dfs(0);
		System.out.println(sb);
	}
	
	static void dfs(int cnt) {
		
		//M개를 골랐으면 답 배열 StringBuilder에 Append
		if(cnt==M) {
			for(int n : ans) {
				sb.append(n).append(" ");
			}
			sb.append("\n");
			return;
		}
		
		//이전에 추가된 값이랑 같은 값이 추가되면 중복 탐색이 일어나므로 이전 추가된 값을 저장할 before 추가
		int before = 0;
		
		for(int i = 0;i<N;i++) {
			//방문하지 않았고 바로 이전에 추가된 값이 아니라면 탐색
			if(!v[i]&&before!=nums[i]) {
				v[i] = true;
				ans[cnt] = nums[i];
				//이전에 추가된 값 갱신
				before = nums[i];
				dfs(cnt+1);
				v[i] = false;
				
			}
		}
	}
}

```


